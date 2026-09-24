**By the end of this practical you should be able to:** <br/>
* [ ] use the terminal to navigate to where your MRI data for this course will be <br/>
* [ ] open MR images with fsleyes <br/>
* [ ] distinguish between structural and functional images in contrast, resolution, and dimensions <br/>
* [ ] use fsleyes to identify the coordinates and intensity at the cursor location, and toggle images on/off <br/>
* [ ] view the timeseries of a functional image and understand what it means
<br/>

**Access FastX** through the remote login: <br>
https://fastx.divms.uiowa.edu:3443/  <br/>
<br/>


**First prep step**, make a folder for holding data for our labs: <br/>
*  Open your terminal by clicking on the icon showing a little black screen
*  Type `pwd`. Where are you in the computer filesystem?
*  Type `ls`. What other files are here? 
*  To make a new folder using the terminal type `mkdir fmriLab`
*  Move yourself into the folder with data by typing `cd fmriLab`


**Second prep step**, download some images: <br/>
*  Copy/paste `wget -O lab01_images.tar.gz https://osf.io/bprq5/download/`
*  Use commands introduced above to see what was downloaded
*  To unpack the download copy/paste `tar -xvf lab01_images.tar.gz`
*  Move yourself into the folder with data by typing `cd osfshare`
<br/>

**Open fsleyes**: <br/>
*  Open fsleyes by typing `fsleyes &`
  *  The `&` at the end tells the terminal to run this program in the background, meanwhile you still have access to the terminal to run other commands
<br/>

**Open an image with fsleyes**: <br/>
*  Click on `File` -> `Add from file`
*  Open the file named `sub-97-T1w_defaced.nii.gz`
*  Overlay another file, open the file named `sub-97-T1w_brain.nii.gz`
*  Change the color scale of the top image to see what is different
<br/>

**Understanding the T1 image: Try to answer these questions with your neighbors** <br>
>   1.0. "defaced" means the face has been removed from the image, why do you think we did that? How does the defaced image differ from the other image we added? <br>
>   1.1. What kinds of tissues are the brightest and darkest? <br>
>   1.2. Place your cursor at different places in the image and see how it affects coordinates  <br>
>   1.3. In addition to the coordinate location of your cursor, what additional information is being shown here? <br>
>   1.4. How many dimensions are there in the image? <br>
>   1.5. What do the letters on the four sides of each view shown below mean?  <br>
<br/>


**Add a functional image on top of the structural**: <br/>
*  Use steps learned from above to add a new image
*  Add the file named `sub-97_task-flanker_bold.nii.gz`
*  Place cursor in the brain somewhere and then toggle on/off the functional image using this button 
![Introduction-to-FSLeyes_toggle-eye-fsleyes](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/053288c2-8086-4b68-b2cf-5b5ee4598da1)
<br/>

**Try to answer these questions with your neighbors** <br>
>  2.0. Does the functional image have more or less anatomical detail than the structural T1 image? <br>
>  2.1. What kinds of tissues are the brightest and darkest? <br>
>  2.2. How many dimensions are there in the functional image? <br>
>  2.3. Use the menu at the top-left of your screen to view the BOLD timeseries for a voxel: View -> Time Series. How does the timeseries compare inside vs. outside the brain? What do the numbers represent for the y-axis of the timeseries? <br>
<br>

**Example with timeseries viewer on:** <br>
![Introduction-to-FSLeyes_time-series](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/e88cfa75-3fc9-4fc4-af3f-415ace30c713)


<br/>