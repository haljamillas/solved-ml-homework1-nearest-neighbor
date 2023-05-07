Download Link: https://assignmentchef.com/product/solved-ml-homework1-nearest-neighbor
<br>
. <strong>Nearest Neighbor. </strong>In this question, we will study the performance of the Nearest Neighbor (NN) algorithm on the MNIST dataset. The MNIST dataset consists of images of handwritten digits, along with their labels. Each image has 28×28 pixels, where each pixel is in grayscale scale, and can get an integer value from 0 to 255. Each label is a digit between 0 and 9. The dataset has 70,000 images. Althought each image is square, we treat it as a vector of size 784.

The MNIST dataset can be loaded with sklearn as follows:

&gt;&gt;&gt; from sklearn.datasets import fetch_openml

&gt;&gt;&gt; mnist = fetch_openml(’mnist_784’)

&gt;&gt;&gt; data = mnist[’data’]

&gt;&gt;&gt; labels = mnist[’target’]

Loading the dataset might take a while when first run, but will be immediate later. See http://scikit-learn.org/stable/datasets/mldata.html for more details. Define the training and test set of images as follows:

&gt;&gt;&gt; import numpy.random

&gt;&gt;&gt; idx = numpy.random.RandomState(0).choice(70000, 11000)

&gt;&gt;&gt; train = data[idx[:10000], :].astype(int)

&gt;&gt;&gt; train_labels = labels[idx[:10000]]

&gt;&gt;&gt; test = data[idx[10000:], :].astype(int)

&gt;&gt;&gt; test_labels = labels[idx[10000:]]

It is recommended to use numpy and scipy where possible for speed, especially in distance computations.

<ul>

 <li>Write a function that accepts as input: (i) a set of images; (ii) a vector of labels,corresponding to the images (ii) a query image; and (iii) a number <em>k</em>. The function will implement the <em>k</em>-NN algorithm to return a prediction of the query image, given the given label set of images. The function will use the <em>k </em>nearest neighbors, using the Euclidean L2 metric. In case of a tie between the <em>k </em>labels of neighbors, it will choose an arbitrary option.</li>

 <li>Run the algorithm using the first <em>n </em>= 1000 training images, on each of the test images, using <em>k </em>= 10. What is the accuracy of the prediction (measured by 0-1 loss; i.e. the percentage of correct classifications)? What would you expect from a completely random predictor?</li>

 <li>Plot the prediction accuracy as a function of <em>k</em>, for <em>k </em>= 1<em>,…,</em>100 and <em>n </em>= 1000. Discuss the results. What is the best <em>k</em>?</li>

 <li>Using <em>k </em>= 1, run the algorithm on an increasing number of training images. Plot the prediction accuracy as a function of <em>n </em>= 100<em>,</em>200<em>,…,</em> Discuss the results.</li>

</ul>