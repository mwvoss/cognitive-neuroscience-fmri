**By the end of this practical you should be able to:**

- [ ] Use the terminal to navigate to where your MRI data for this course will be
- [ ] Open MR images with FSLeyes
- [ ] Distinguish between structural and functional images in contrast, resolution, and dimensions
- [ ] Use FSLeyes to identify the coordinates and intensity at the cursor location, and toggle images on/off
- [ ] View the time series of a functional image and understand what it means

**Access FastX** through the remote login:

https://fastx.divms.uiowa.edu:3443/

**First prep step:** Make a folder for holding data for our labs.

- Open your terminal by clicking on the icon showing a little black screen.
- Type `pwd`. Where are you in the computer filesystem?
- Type `ls`. What other files are here?
- To make a new folder using the terminal, type `mkdir fmriLab`.
- Move yourself into the folder with data by typing `cd fmriLab`.

**Second prep step:** Download some images.

- Copy/paste `wget -O lab01_images.tar.gz https://osf.io/bprq5/download/`.
- Use commands introduced above to see what was downloaded.
- To unpack the download, copy/paste `tar -xvf lab01_images.tar.gz`.
- Move yourself into the folder with data by typing `cd osfshare`.

**Open FSLeyes:**

- Open FSLeyes by typing `fsleyes &`.
    - The `&` at the end tells the terminal to run this program in the background. Meanwhile, you still have access to the terminal to run other commands.

**Open an image with FSLeyes:**

- Click on `File` → `Add from file`.
- Open the file named `sub-97-T1w_defaced.nii.gz`.
- Overlay another file: open the file named `sub-97-T1w_brain.nii.gz`.
- Change the color scale of the top image to see what is different.

**Understanding the T1 image: Try to answer these questions with your neighbors.**

1. "Defaced" means the face has been removed from the image. Why do you think we did that? How does the defaced image differ from the other image we added?
2. What kinds of tissues are the brightest and darkest?
3. Place your cursor at different places in the image. How does this affect the coordinates?
4. In addition to the coordinate location of your cursor, what additional information is being shown here?
5. How many dimensions are there in the image?
6. What do the letters on the four sides of each view shown below mean?

**Add a functional image on top of the structural:**

- Use the steps learned above to add a new image.
- Add the file named `sub-97_task-flanker_bold.nii.gz`.
- Place the cursor somewhere in the brain and then toggle the functional image on/off using this button:

![Introduction-to-FSLeyes_toggle-eye-fsleyes](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/053288c2-8086-4b68-b2cf-5b5ee4598da1)

**Try to answer these questions with your neighbors.**

1. Does the functional image have more or less anatomical detail than the structural T1 image?
2. What kinds of tissues are the brightest and darkest?
3. How many dimensions are there in the functional image?
4. Use the menu at the top-left of your screen to view the BOLD time series for a voxel: `View` → `Time Series`. How does the time series compare inside vs. outside the brain? What do the numbers represent for the y-axis of the time series?

**Example with time series viewer on:**

![Introduction-to-FSLeyes_time-series](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/e88cfa75-3fc9-4fc4-af3f-415ace30c713)
