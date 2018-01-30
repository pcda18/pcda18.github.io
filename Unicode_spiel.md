##  Character Encoding is Tricky
### The Big Difference Between Python 2.7 and Python 3

In Python 2, a "str" object — i.e., a text string — is typically encoded in 8-bit ASCII, or "extended ASCII," while Python 3 uses Unicode by default. 8-bit extended ASCII has 256 options for each unit in a string of characters, while Unicode can in theory represent 1.1 million characters (though the standard only includes ~140,000 characters at the moment).

Every character in a text file is represented by a number from zero to some maximum value, expressed in binary 1s and 0s. Old-school ASCII (the plainest of plain text), is a 7-bit encoding format. Because 2^7 = 128, 7-bit ASCII gives you a maximum of 128 possible characters. The capital letter "A" corresponds to 65 in decimal, or 1000001 in binary. "B" is decimal 66, or 1000010, and so on.

Each number in a given character encoding format is called a "code point." Here's a handy table of ASCII code points:
https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/ASCII-Table-wide.svg/1024px-ASCII-Table-wide.svg.png

If you use 8 bits instead of 7 to represent an ASCII character, you get 8-bit extended ASCII: 256 options instead of 128. (8 bits, incidentally, is known as a "byte.") Where things get tricky is that different encoding formats have used those extra 128 options differently over the years.

Unicode offers a much larger character set, encompassing just about every written script now in use around the world, as well as characters for many long-dead languages. It includes Egyptian hieroglyphics, Sumero-Akkadian cuneiform, ornamental dingbats, and all the emojis. For instance, the decimal code point for the "Smiling Face With Heart-Eyes" emoji in Unicode is 128525.

At a high level, the Unicode standard simply maps code points (numbers) to characters. In practice, there are a handful of ways to actually encode it. If you want to be very explicit and don't care about wasting disk space and bandwidth, there's a format called UTF-32 that uses 32 bits to represent each character. UTF-8, however, is far more common.

For the first 128 code points, Unicode is identical to ASCII. A plaintext document stored as 8-bit extended ASCII is *also* perfectly valid UTF-8. For code points above that, UTF-8 uses what's known as "variable-width encoding." For less common characters (less common in English, anyway), UTF-8 uses multiple bytes to represent a single character. If a computer is reading a series of bytes and it finds one higher than the first 128, it knows that it's dealing with a multi-byte character. There's a system of definitions for "lead units" and "trail units" in UTF-8; suffice it to say that a single character can be represented by 1, 2, 3, or 4 bytes in a row. It sounds complicated, but properly encoded UTF-8 is guaranteed to be orderly and unambiguous. Unicode has its origins in the late '80s/early '90s, and it took many years for it to be adopted widely.

People started using old-school, 7-bit ASCII in the early '60s. As complex word processors and personal computers rolled out in the '70s and '80s, system designers (especially those catering to markets in languages other than English) wanted to use more than just 128 characters. By using 8 bits instead of 7, you could sell a word processor with up to 128 additional characters. The result was a mess: Many manufacturers in many countries created their own encoding systems for their own particular needs. Since people weren't using the Internet, it wasn't immediately necessary to get everyone on the same page.

The International Standards Organization (ISO) tried to rein in the chaos in the 1980s: They introduced a series of 8-bit text encoding standards, each tailored to a particular region. The most widely used of these standards was designed for Western European languages: ISO-8859-1, a.k.a. "ISO Latin 1" or "latin1". Much of the Web was encoded in ISO Latin 1 in the '90s and 2000s, and plenty of those pages are still around. You can find a list of ISO Latin 1 characters here:
https://cs.stanford.edu/people/miles/iso8859.html

So, for example, if a program reads the Unicode character "é" (represented by two bytes), but it thinks it's reading ISO Latin 1, it would display "Ã©" instead.

So a "str" object in Python 2, by default, is just a string of bytes: one byte after another, no matter how the text you're reading was encoded. Each byte is a value between 00000000 and 11111111, no questions asked. In short, in Python 2 it's up to the programmer to make sure their bytes make sense.

Python 2 can work with Unicode strings, but it takes a bit of extra effort. Since they're generally the exception, they're denoted by a 'u' before the first quotation mark, like so:

some_variable_name = u'This is a Unicode string in Python 2.'

In Python 3, a "str" object is Unicode by default: Each unit in the string is just a single code point in the Unicode standard. Python 3 can also work with byte strings, but it too takes extra effort. Since they're the exception, byte strings are represented in Python 3 with a 'b' before the quotation mark, like so:

some_variable_name = b'This is a byte string in Python 3.'

Ultimately, the problem with Python 2 is that it might not throw an error if you try to combine a Unicode string and a byte string, or if you combine byte strings encoded in multiple extended ASCII formats. This can lead to maddeningly hard-to-find bugs if you're not cautious.

Python 3, by contrast, makes you explicitly specify character encoding details if you're loading text from a format other than Unicode. If you're working with UTF-8, you should be A-OK. We can open a UTF-8 file called "pg623.txt" like so:

pathname = "/sharedfolder/pg623.txt"
swift_lines = open(pathname).read().splitlines()

Just to be safe, the urllib package in Python 3 will download text from the web as a byte stream, so you need to explicitly tell it to convert the text to Unicode:

from urllib.request import urlopen
url = 'http://example.com/index.html'
a_web_page = urlopen(url).read().decode('utf8')

So that's my argument for using Python 3 instead of Python 2 for text processing. You may end up seeing a few more errors at the start of a project, but using Unicode for everything will save time and preserve your sanity once you start mixing real-world datasets together.


                             -- Steve McLaughlin


                              ___, ____   ____, ___,
                             (-|_)(-/  ` (-|  \(-|_\_,
                              _|    \___, _|__/ _|  )
                             (           (     (      2018
