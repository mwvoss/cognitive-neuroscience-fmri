**By the end of this practical you should be able to complete preprocessing on your data with the following steps:**

- [ ] Use FSL's [BET](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/BET/UserGuide) tool to remove the skull from a T1 image
- [ ] Use FSLeyes to check the output of `BET`

**Access FastX** through the remote login:

https://fastx.divms.uiowa.edu:3443/

**In the terminal, move to the folder where our downloaded data is:**

- At the terminal prompt, type `cd fmriLab`
- Type `ls` and you should see the data you downloaded as a folder named `flankerData_n4`

**Using FSL's Brain Extraction Tool (BET) to skull-strip:**

- At the prompt, type `fsl`
- Click the **BET brain extraction** button on the FSL menu
- Set up `BET`:
    - Click the yellow folder to select your defaced T1 image with skull as your **Input Image**
    - FSL will automatically fill in the **Output Image** with the same filename as your T1 and `_brain` at the end
    - Expand **Advanced Options**
        - Select **Output binary brain mask image**
    - Select **Go** to run `BET`
- Example default settings:

![betDefault](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/b39c96b4-29ba-455d-9135-f74f5b8d2eec)

**Checking BET:**

- Use the GUI menu to open your defaced T1 and brain mask in FSLeyes
- Use the **Opacity** slider to make the mask transparent so you can see the brain image in the background
- Use this checklist:
    - [ ] **Top of the brain:** Does the mask cover the brain without spilling into the eyes or skull?
    - [ ] **Bottom of the brain:** Does the mask "hug" the brainstem without spilling into the throat?

**Modifying BET settings:**

- Open or return to the BET GUI
- An advanced option that often helps: use the dropdown menu to select **Robust brain centre estimation**
- If your mask was too small or too large at the top of the brain, change the **Fractional intensity threshold**
- If your mask was too small or too large at either the top or bottom of the brain, change the **Threshold gradient**

![betMods](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/5b5a6a4f-fffb-4a25-8920-c1c52e6e6839)
