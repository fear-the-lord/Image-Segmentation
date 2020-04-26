# Image-Segmentation
Image Segmentation using U-NET Architecture

<h2>Problem Statement</h2>
<p>Find the nuclei in divergent images to advance medical discovery.</p>

<hr style="width:50%; text-align:left; margin-left:0">

<h2>Overview</h2>
<p>This problem has been given in the 2018 Data Science Bowl in Kaggle. We aim to create an algorithm to automate nucleus detection. By automating nucleus detection we could unlock cures faster, from rare disorders to common cold. Identifying the cells’ nuclei is the starting point for most analyses because most of the human body’s 30 trillion cells contain a nucleus full of DNA, the genetic code that programs each cell. Identifying nuclei allows researchers to identify each individual cell in a sample, and by measuring how cells react to various treatments, the researcher can understand the underlying biological processes at work.</p>

<hr style="width:50%; text-align:left; margin-left:0">

<h2>Things to do</h2>
<ul>
  <li>Import the necessary dependencies.</li>
  <li>Load the dataset.</li>
  <li>Define the image dimensions.</li> 
  <li>Resize the image and masks according to the defined image dimensions.</li>
  <li>Build the U-NET Model accoriding to the requirements.</li>
  <li>Train the model.</li>
  <li>Make Predictions.</li>
  <li>Show the output.</li>
 </ul>
 
 <hr style="width:50%; text-align:left; margin-left:0">
 
 <h2>Dependencies</h2>
 <ul>
  <li>TensorFlow</li>
  <li>OS</li>
  <li>Numpy</li>
  <li>Matplotlib</li>
  <li>Scikit Learn</li>
  <li>TQDM</li>
  <li>Random</li>
 </ul>
 
 <hr style="width:50%; text-align:left; margin-left:0">
 
 <h2>Resizing the image and masks.</h2> 
 <p>The datset can be obtained from the following link: <a href="https://www.kaggle.com/c/data-science-bowl-2018/data">Dataset Link.</a>
  The datset is divided into two parts:<br>
  <ul>
    <li><b>stage1_train:</b> contains the images and annotated masks.</li><br>
    <li><b>stage1_test:</b> contains the images used for testing the model.</li><br>
  </ul></p>
  <br>
  <p>This dataset contains a large number of segmented nuclei images. The images were acquired under a variety of conditions and vary in     the cell type, magnification, and imaging modality (brightfield vs. fluorescence). The dataset is designed to challenge an               algorithm's ability to generalize across these variations. Each image is represented by an associated <b>ImageId</b>. Files             belonging to an image are contained in a folder with this ImageId. Within this folder are two subfolders: <br>
  <ul>
    <li><b>images:</b> contains the image file.</li><br>
    <li><b>masks:</b> contains the segmented masks of each nucleus. This folder is only included in the training set. Each mask contains      one nucleus. Masks are not allowed to overlap (no pixel belongs to two masks).</li><br>
  </ul></p>
  <p>The images and masks of the training set are converted to a fixed dimensions of <b>128*128*3</b>. The images of the test set are converted      to the same dimensions of <b>128*128*3</b>. Create a numpy array <b>X_train</b> to store the image pixels of the training set and another      numpy array <b>Y_train</b> to store the the merged mask pixels of each image of the training set. Store the image pixels of the          test set and store it in a numpy array named <b>X_test</b>.</p>
  
   <hr style="width:50%; text-align:left; margin-left:0">
   
  <h2>U-NET Architecture</h2>
  <p>The U-NET was developed by Olaf Ronneberger et al. for Bio Medical Image Segmentation. The architecture contains two paths. First path is the <b>contraction path</b> (also called as the encoder) which is used to capture the context in the image. The encoder is just a traditional stack of convolutional and max pooling layers. The second path is the <b>symmetric expanding path</b> (also called as the decoder) which is used to enable precise localization using transposed convolutions. Thus it is an end-to-end fully convolutional network (FCN), i.e. it only contains Convolutional layers and does not contain any Dense layer because of which it can accept image of any size.</p>
  
  <p>This is a pretty simple architecture and easy to implement architecture. The link to the paper is: <a href="https://arxiv.org/pdf/1505.04597.pdf">Paper Link.</a>
  
  <p> The architecture has been modified as per the rquirements for this project. The details of the modified architecture is given below: <br>
  <img src = "https://user-images.githubusercontent.com/35571958/80313619-9c80ee80-8809-11ea-9f3a-c165077175ce.png"></img>

  <hr style="width:50%; text-align:left; margin-left:0">


 
  
