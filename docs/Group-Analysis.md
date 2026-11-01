# Lab: Group-Level fMRI Analysis in FSL FEAT

## Learning objectives

By the end of this practical, you should be able to:

- [ ] Use the FEAT GUI to create a group-level map of task-related BOLD activation.
- [ ] Locate and interpret group-level results using the FEAT HTML report.

## Before you begin

**Access FastX:** [FastX remote login](https://fastx.divms.uiowa.edu:3443/).

**Prerequisite:** You should have completed the first-level analyses for `sub-001`, `sub-002`, `sub-003`, and `sub-004`. Each subject should have a `flanker.feat` output directory.

In this lab, we will combine the four subjects' first-level results to examine the average activation for each of the six contrasts from the single-subject analyses:

- Congruent > baseline (`con > baseline`)
- Neutral > baseline (`neu > baseline`)
- Incongruent > baseline (`inc > baseline`)
- Errors > baseline (`errors > baseline`)
- Incongruent > neutral (`inc > neu`)
- Congruent > neutral (`con > neu`)

## 1. Open the group-analysis GUI

1. Open a terminal and move to your data directory:

    ```bash
    cd ~/fmriLab/
    ```

2. Type `fsl` and select **FEAT FMRI analysis**.
3. In the top-left menu of FEAT, select **Higher-level analysis**.

![Higher-level analysis option in FEAT](https://github.com/mwvoss/PSY4025_FA23/assets/24663988/2c8c866a-2440-40ee-8c9e-46720748132c)

## 2. Data tab: Select input and output directories

- [ ] Keep **Inputs are lower-level FEAT directories** selected.
- [ ] Set **Number of inputs** to `4`, because we have four subjects.
- [ ] Click **Select FEAT directories** and select the `flanker.feat` directory for each subject.

![Four subject FEAT input directories](images/feat-group_input-subs.png)

- [ ] Keep **Use lower-level copes** selected. These correspond to the six contrasts specified in the first-level analyses.
- [ ] Set the output directory within `derivatives`, naming the group-level output `group_n4`.

![Group-level output directory](images/feat-group_output-dir.png)

## 3. Stats tab: Set up the group model

- [ ] Select **Fixed effects**.
- [ ] Select **Model setup wizard**.
- [ ] Keep the default **Single-group average** model and click **Process**.

![FEAT group model wizard](images/feat-group_model-wizard.png)

**Why fixed effects?** In this teaching example, we are estimating the average effect for these four participants. A fixed-effects analysis does **not** support generalizing the result to a larger population. We are using it to learn the group-analysis workflow with a very small sample.

### Inspect the group model

![Group model](images/feat-group_model-group.png)

**Discuss:** What does the red line represent in the group model? How does this model combine information across the four participants?

## 4. Post-stats tab

- [ ] Leave the **Post-stats** settings at their defaults for this lab.

## 5. Run the analysis and inspect the report

1. Click **Go** to run the higher-level FEAT analysis.
2. When the analysis finishes, open its HTML report. It may open automatically in your browser; otherwise, find it in your group-level output directory.

### Check the registration summary

- [ ] Open **Registration summary**.
- [ ] Confirm that the expected four subjects are included.
- [ ] Inspect the image overlays: are the brains aligned as expected in standard space?

### Examine the group-level activation maps

1. Open **Results**.
2. Select **Lower-level contrast 3 (`inc`)**.
3. Compare your output with the example below.

![Group-level activation map for incongruent condition](images/feat-group_group-map-inc.png)

- [ ] Confirm that the expected contrast is displayed.
- [ ] Look for plausible activation clusters and any obvious image artifacts.

### Examine the statistical results table

Click the activation image in the HTML report to view the corresponding results table.

![Group-level results table for incongruent condition](images/feat-group_group-table-inc.png)

**Discuss:** What information is reported in the table? How does it relate to the activation map?

## 6. Lab submission: Evidence of completion

Submit **two PDFs from your higher-level FEAT analysis** to the lab assignment on ICON.

1. **Registration summary PDF:** Open **Registration summary** in your higher-level FEAT HTML report and print/save it as a PDF. The TA will check that the expected subjects are included and that the image underlays and overlays are aligned appropriately.
2. **Group results PDF for `con > neu`:** In the **higher-level FEAT HTML report**, open the results summary for the `con > neu` contrast and print/save that page as a PDF. The TA will check that the analysis completed and that the expected contrast and statistical map are present.

**Before submitting, verify:**

- [ ] Both PDFs come from the **higher-level** group analysis (`group_n4`), not an individual subject's `flanker.feat` report.
- [ ] The registration PDF shows the expected input subjects and alignment.
- [ ] The results PDF is for the **`con > neu`** contrast.
- [ ] Both PDFs are readable and uploaded to ICON.
