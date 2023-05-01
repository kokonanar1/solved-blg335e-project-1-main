Download Link: https://assignmentchef.com/product/solved-blg335e-project-1-main
<br>
<span class="kksr-muted">Rate this product</span>

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2022/04/625.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

<noscript>

 <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2022/04/625.png?w=980&amp;ssl=1" data-recalc-dims="1">

</noscript>

Ren´e Goscinny &amp; Albert Uderzo, Asterix and The Big Fight

<ul>

 <li>You should write all your code in Python language.</li>

 <li>Cheating is highly discouraged.</li>

 <li>Ninova only stores files under 25 MB. If you could not upload your results, you can share them with me via Dropbox, or send me private YouTube video links for each part’s results.</li>

 <li>In this homework, we will work on high resolution images. But you are free to resize them if your system is not capable to work on them.</li>

</ul>

<h1>1    – Part 1: “I am feeling blue”</h1>

In this homework, we will use image sequences from DAVIS Challenge<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> which is a dataset originally created for semantic segmentation. You can download the <strong>“TrainVal” </strong>set

1

<h2>                         BLG453E                                                     Homework-1</h2>

<h2>Table 1: Some example images from DAVIS challenge and their segmentation maps</h2>

which contains image sets and their semantic annotations<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a>. I also selected and uploaded some of them under my website<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a>. Some of the image sequences and their segmentation maps are given in Table 1.<strong>You must select and obtain video results for at least 3 image sequences for each part of the homework.</strong>

This part of the homework focuses on an introductory problem especially for students who are not comfortable with numpy and OpenCV libraries.<a href="#_ftn4" name="_ftnref4"><sup>[4]</sup></a> In this part, we will

<ul>

 <li>Read images and image segmentation maps from the specified folders.</li>

 <li>Mask some color channels of an object using the segmentation map. You can select one or more color channels to mask.</li>

 <li>Write the obtained frames as a video.</li>

</ul>

To read an image in OpenCV, you can use <em>cv</em>2<em>.imread </em>function. As shown in the code below, for segmentation maps, you should use <em>cv</em>2<em>.IMREAD GRAY SCALE </em>flag. Since the segmentation maps are saved as indexed images (images that contain ids for pixels, not color values), reading without that flag makes it more difficult to use these maps. The following code shows how to read a sequence of images and do some operations on them. You can start from this skeleton code.

<table width="564">

 <tbody>

  <tr>

   <td width="30">for</td>

   <td width="534">i             in range ( len ( all images ) ) :image = cv2 . imread( main img dir +all images [ i ])# Image is a numpy array with shape (800 , 1920 , 3) seg = cv2 . imread( main seg dir +all images [ i ] . split ( ’ . ’ ) [0]+ ’ . png ’ , cv2 .IMREAD GRAYSCALE)#Seg is the segmentation map of the image with shape (800 , 1920) seg = ( seg == 38)#I know that seg has maps for objects with IDs 38 and 75. Thus I changed it into a binary map for 38.</td>

  </tr>

 </tbody>

</table>

1

3

5

7

2

<table width="564">

 <tbody>

  <tr>

   <td width="426">image without the guy = ##Show your work here image of the guy = ##Show your work hereimage of the guy [ : , : , 1 : 3 ] = ##Show your work here .                   Ivalues of red and green channels by 75%. image = ( image without the guy + image of the guy )#cv2 . imwrite ( ’x . png ’ , image)#You can use imwrite              function           to check the                  results .</td>

   <td width="73">decreased</td>

   <td width="65">the</td>

  </tr>

 </tbody>

</table>

9

11

13

15

17

To save the images as a video you can use moviepy library. I personally prefer this simple but effective library rather than OpenCV’s video writing operations (You are also free to use OpenCV’s operations.). You can create an ImageSequenceClip object and write a video as given in the following lines. (<strong>Note: </strong>While OpenCV uses BGR channel order by default, moviepy uses RGB.)

<table width="564">

 <tbody>

  <tr>

   <td width="564">images list = [ ]##Add the processed images to the                             l i s t .clip = ImageSequenceClip ( images list , fps=25) clip . write videofile ( ’ part1 video .mp4’ , codec=’mpeg4 ’ )</td>

  </tr>

 </tbody>

</table>

2

4

6

You can find an example output frame at Figure 1.

Figure 1: Task 1

<h1>2    – Part 2: Histogram matching</h1>

In this part of the homework you will do histogram matching between video frames and a target image. To do this, you have two options:

<h2></h2>

<ul>

 <li>Obtain a histogram for each video frame and use the average of them.</li>

 <li>Obtain a huge image which is a concatenation of all images and use this image’s histogram.</li>

</ul>

You can select the bin count according to the results. You are also free to select the target image. An example is shown in Figure 2.

Figure 2: Task 2

<h1>3     – Part 3: Histogram matching from segmentation maps</h1>

Finally, you will use multiple target images to assign different targets to different objects. An example result is shown in Figure 3. <strong>For each object, use only the color values from the selected object. Think of each object separately.</strong>

<h2>Figure 3: Task 3</h2>

4

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="https://davischallenge.org/">https://davischallenge.org</a>

<a href="#_ftnref2" name="_ftn2">[2]</a> <a href="https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-Unsupervised-trainval-Full-Resolution.zip">https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-Unsupervised-trainval</a><a href="https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-Unsupervised-trainval-Full-Resolution.zip">Full-Resolution.zip</a>

<a href="#_ftnref3" name="_ftn3">[3]</a> <a href="http://web.itu.edu.tr/sahinyu/DAVIS-JPEGImages.zip">http://web.itu.edu.tr/sahinyu/DAVIS-JPEGImages.zip</a>