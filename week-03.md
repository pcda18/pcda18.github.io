## Week 3 Outline: Data Modeling

#### Install LibreOffice

Before we start class, download and install LibreOffice:
- [https://www.libreoffice.org/](https://www.libreoffice.org/)

#### Launching Docker

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

#### Notebook Files

Save the following Jupyter notebook files to `sharedfolder` on your desktop.

- [3.1 CSV Input/Output](https://github.com/pcda18/pcda18.github.io/blob/master/Week-03.1_CSV-Input-Output.ipynb)

- [3.2 CSV Input/Output Continued](https://github.com/pcda18/pcda18.github.io/blob/master/Week-03.2_CSV-Input-Output-Continued.ipynb)

- [3.3 MoMA Metadata Visualizations](https://github.com/pcda18/pcda18.github.io/blob/master/Week-03.3_MoMA_Metadata_Visualizations.ipynb)

- [3.4 Cassette Label Date Reformatting](https://github.com/pcda18/pcda18.github.io/blob/master/copy_me/Cassette_Date_Reformat.ipynb)

Now go to [localhost:8889](localhost:8889) in your browser and open the notebook file `Cassette_Date_Reformat.ipynb` in Jupyter.


#### Sample CSV Data

Sample datasets from The Museum of Modern Art ([MoMA](https://github.com/MuseumofModernArt/collection)) in CSV format. Download these files to `sharedfolder` on your desktop:

- [Artists.csv](https://media.githubusercontent.com/media/MuseumofModernArt/collection/master/Artists.csv)
- [Artworks.csv](https://media.githubusercontent.com/media/MuseumofModernArt/collection/master/Artworks.csv)
