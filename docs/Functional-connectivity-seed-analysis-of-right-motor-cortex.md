# Hands on Practical for Resting-state Functional Connectivity

For this hands on lab practice, we will be using data from sub-001 that you downloaded and processed for the previous block. 

They should be located at `~/fmriLab/flankerData_n4/`, and you should be able to navigate to it by doing `cd ~/fmriLab/flankerData_n4`.   

You should also have the "skull-striped T1 image" saved under `~/fmriLab/flankerData_n4/sub-001/anat/` 


## What you will learn from this lab practice
- How to replicate this famous finding from Biswal 1995 
<img width="293" alt="practical-rsfc_biswal-map" src="https://github.com/mwvoss/PSY4025_FA23/assets/24663988/edb6edaf-b0dd-4c3a-a3c5-367613ffaa8b">


- Understand how to preprocess fMRI data for resting-state functional connectivity analysis
- Understand how to extract and input a "seed" timeseries to search for brain regions that show resting-state connectivity with this "seed" region of interest.


## Step 1, preprocess resting-state fMRI data
We will use the steps you learned from last block to preprocess the resting-state data.

- Let's use FEAT again to set up preprocessing
    - Go to the subject folder and launch FSL
        * `cd ~/fmriLab/flankerData_n4/sub-001/func`
        * `fsl`
    - In FSL GUI, open 'FEAT FMRI analysis'
        - Define scope of 'First-level analysis' to 'Preprocessing' at the top of the GUI
        - Select `sub-001-task-rest_bold.nii.gz` as input 4D. 
        - Set output to `~/fmriLab/flankerData_n4/sub-001/func/rest_rmot.feat`
        - We will delete the first 4 volumes in `Delete volumes`
        - Leave the High pass filter cutoff (s) to 100s

    - Go to the Pre-stats tab. We will do the following preprocessing
        - Motion correction with `MCFLIRT`
        - Select `BET`
        - Spatial smoothing of 6 mm
        - select `Highpass`

    - Go to the Registration tab, do the following:
        - Select `Main Structural Image`
        - Select the "brain extracted" T1 as the main structural image 
        - Change to normal search and 12 DOF
        - For standard space, change to normal search and 12 DOF 

- Hit Go!

- We then need to manually do "low-pass" filter. That is because FEAT does not support it (only does highpass). We have to do it via command line in the terminal.
  - Now open the terminal, move to the `rest_rmot.feat` folder you just made: `cd ~/fmriLab/flankerData_n4/sub-001/func/rest_rmot.feat`
  - Note, this might not work if you didn't save rest_rmot.feat under sub-001, in that case you have to find our where you saved it.
  - Then run this command:
`fslmaths filtered_func_data.nii.gz -bptf -1 2.5 filtered_func_data.nii.gz`
- Here we are doing lowpass filtering of 0.08 hz. 
    - the `-bptf` option expects a high-pass sigma and a low-pass sigma, which can be caluclated by
    - `highpass_sigma = 1 / (2.35 * TR * HP_freq)` (we use "-1" because we already highpassed the data)
    - `lowpass_sigma = 1 / (2.35 * TR * LP_freq))` (remember TR is 2s)
    - If interested in an explanation for this, see here: https://www.jiscmail.ac.uk/cgi-bin/webadmin?A2=fsl;fc5b33c5.1205 


## Step 2. Locate a seed region of interest in fsleyes 

- Stay in the preprocessed output folder `~/fmriLab/flankerData_n4/sub-001/func/rest_rmot.feat/`

- Locate the right motor cortex
  - Use fsleyes to open up the preprocessed structural image
     - `file`, `add from file`, goto `reg`, select `highres`
  - Also add the `filtered_func_data` 
  - In the Overlay list panel, select filtered_func_data image 
  - To navigate to the right motor cortex, enter the following x y z coordinate for scanner anatomical space: \
x=34 (top row), y=-12 (middle row), z=24 (lower row)
  - With the filtered_func_data selected, select View -> Timeseries, and you should see a timeseries plot on the bottom panel of fsleyes, like below

<img width="80%" height="80%" alt="funcTimeseries" src="https://github.com/user-attachments/assets/fd84c8ea-9f58-4015-824f-e50b3fc2ef3f" />

  - Now if you toggle UP the structural image, you can see the timeseries is from the hand "knob" area of the right motor cortex

<img width="80%" height="80%" alt="funcTimeseriesWithStruc" src="https://github.com/user-attachments/assets/9fa859b0-1392-400c-8316-031c61e4d43c" />


## Step 3. Add another timeseries from the left motor cortex to see their coupling, or functional connectivity
   - We will now add another timeseries in the same network, to see the coupling of the right and left motor cortex at rest
   - Scale the right motor cortex timeseries by selecting Plotting mode: Normalised 
   - Add the normalised plot to be "fixed" in the timeseries window by clicking the + in the plot list and keep the line blue
   - Now select the filtered_func_data image again, and enter the following x y z coordinate for scanner anatomical space: \
x=-33 (top row), y=-33 (middle row), z=24 (lower row). Another timeseries will appear in normalised units.
   - Add the new timeseries to also be "fixed" in the timeseries window by clicking the + in the plot list and change the line color to red

<img width="80%" height="80%" alt="Lmot" src="https://github.com/user-attachments/assets/dc776ac5-34c3-46bc-80a2-5b824e785458" />


## Technical Assignment: Demonstrate a completed exercise for our resting state right and left motor cortex plot, and add your own third region of interest 
   - Plot the right motor cortex as shown above in blue
   - Plot the left motor cortex as shown above in red
   - Pick a third region in the brain that you think should NOT have strong functional connectivity with the right motor cortex, and plot it in green. 

<br/>
<br/>
<br/>
