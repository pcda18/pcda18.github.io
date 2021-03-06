## Week 12: Scraping and Clustering


Open Terminal in macOS and launch our Docker container:

```
docker rm -f pcda_ubuntu
docker pull pcda18/ubuntu-image
docker run --name pcda_ubuntu -ti -p 8889:8889 --volume ~/Desktop/sharedfolder/:/sharedfolder/ pcda18/ubuntu-image
```

In Windows 10, open PowerShell and enter the following to launch the Docker container:

```
docker rm -f pcda_ubuntu
docker pull pcda18/ubuntu-image
docker run --name pcda_ubuntu -ti -p 8889:8889 --volume C:\Users\***username_here***\Desktop\sharedfolder:/sharedfolder/ pcda18/ubuntu-image
```

Download a Jupyter notebook from the list below to `sharedfolder` on your desktop.


Navigate to [localhost:8889](localhost:8889) in your browser to open the notebook.


### Jupyter Notebooks


- [New York Times Article Scraper](Week-12_NYT_Article_Scrape.ipynb)

- [Unsupervised Learning: k-means Clustering](Week-12_Clustering.ipynb)

- [Reference Snippets: Strings and Lists](./copy_me/Strings_and_Lists_done.ipynb)


### Resources

- [scikit-learn Cheat Cheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Scikit_Learn_Cheat_Sheet_Python.pdf)

- [scikit-learn Clustering Overview](http://scikit-learn.org/stable/modules/clustering.html)
