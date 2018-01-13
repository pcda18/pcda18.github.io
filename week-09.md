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

Right click the following link and save the Jupyter notebook file to `sharedfolder` on your desktop.


- [Machine Learning 1](https://raw.githubusercontent.com/pcda18/pcda18.github.io/master/Week-09_Machine-Learning.ipynb)


Navigate to [localhost:8889](localhost:8889) in your browser to open the notebook.
