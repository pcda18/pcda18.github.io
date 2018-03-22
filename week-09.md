## Week 9: Your Culture, Your Data / Machine Learning 1



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

Download the following Jupyter notebooks to `sharedfolder` on your desktop.

- [9.0 New York Times Article Scrape](Week-09.0_NYT_Article_Scrape.ipynb)
- [9.1 Supervised Learning](Week-09.1_Supervised-learning.ipynb)
- [9.2 Clustering](Week-09.2_Clustering.ipynb)



Navigate to [localhost:8889](localhost:8889) in your browser to open the notebook.
