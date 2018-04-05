## Week 12: More Text Analysis


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

- [Reference Snippets: Strings and Lists](https://github.com/pcda18/pcda18.github.io/blob/master/copy_me/Strings_and_Lists_done.ipynb)

- [Topic Modeling](Week-12_Topic-Modeling.ipynb)

- [Unsupervised Learning: k-means Clustering](Week-12_Clustering.ipynb)

- [Supervised Learning](Week-12_Supervised_Learning.ipynb)

- [New York Times Article Scraper](https://github.com/pcda18/pcda18.github.io/blob/master/Week-12_NYT_Article_Scrape.ipynb)


### Resources

- [scikit-learn Cheat Cheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Scikit_Learn_Cheat_Sheet_Python.pdf)

- [scikit-learn Classifier Decision Tree](http://scikit-learn.org/stable/tutorial/machine_learning_map/index.html)

- [scikit-learn Clustering Overview](http://scikit-learn.org/stable/modules/clustering.html)

- [scikit-learn Supervised Learning Overview](http://scikit-learn.org/stable/tutorial/statistical_inference/supervised_learning.html)
