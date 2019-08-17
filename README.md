# Fashion MNIST using Neural Network
## 1. Build Model 
Fashion-MNIST is a dataset of Zalando's article images—consisting of a training set of 60,000 examples and a test set of 10,000 examples. Each example is a 28x28 grayscale image. Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel,
with higher numbers meaning darker. This pixel-value is an integer between 0 and 255. The training and test data sets have 785 columns. The first column consists of the class labels and represents the article of clothing. The rest of the columns contain the pixel-values of the associated image. 

Labels
Each training and test example is assigned to one of the following labels:
- 0 T-shirt/top
- 1 Trouser
- 2 Pullover
- 3 Dress
- 4 Coat
- 5 Sandal
- 6 Shirt
- 7 Sneaker
- 8 Bag
- 9 Ankle boot
 
For this experiment, I used Keras which is a high-level API to build and train models and applied Convolutional Neural Network (CNN) which is one of the main categories to do images recognition, images classifications. Objects detections, recognition faces etc., are some of the areas where CNNs are widely used.

Technically, deep learning CNN models to train and test, each input image will pass it through a series of convolution layers with filters (Kernals), Pooling, fully connected layers (FC) and apply Softmax function to classify an object with probabilistic values between 0 and 1. The below figure is a complete flow of CNN to process an input image and classifies the objects based on values.

* <a href="https://ibb.co/kV1j9p"><img src="https://preview.ibb.co/nRkBpp/gec2.jpg" alt="gec2" border="0"></a>

## 2. Dockerize a Keras Application on Jupyter Notebook

### Step-1 : Obtain the docker image
From DockerHub (https://hub.docker.com/r/floydhub/dl-docker/) Docker image is pulled. The image also could automatically built based on the Dockerfile in the Github repo.

```
git clone https://github.com/saiprashanths/dl-docker.git
cd dl-docker
```
![Image of Yaktocat](capture1.png)


Then go to the folder which we want to store the Dockerfile and build docker image.

```
docker build -t floydhub/dl-docker:cpu -f Dockerfile.cpu .
```
![Image of Yaktocat](Capture2.png)

### Step-2 : Run the Docker image as a Container
Once the docker image is built, we are supposed to run a container that uses this image.

```
docker run -it -p 8888:8888 -p 6006:6006 floydhub/dl-docker:cpu jupyter notebook
```
![Image of Yaktocat](capture3.png)
![Image of Yaktocat](capture4.png)
After the above script, we should be able to access Jupyter Notebook (inside the container) from our localhost. The Jupyter notebook has Python (for Keras and Tensorflow) kernel.


### Step-3 : Implement the existing Jupyter code 
Once open the Jupyter notebook, we could upload our existing code and related datasets. We run it in the container and get the output data.
![Image of Yaktocat](capture5.png)
