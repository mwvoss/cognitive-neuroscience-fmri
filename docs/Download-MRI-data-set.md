**Access FastX** through the remote login: <br>
https://fastx.divms.uiowa.edu:3443/  <br/>
<br/>

**Open terminal and move to your fmriLab folder**:<br/>
*  open your terminal application 
*  at the prompt, move to the bids directory in the terminal by typing `cd ~/fmriLab/`
*  copy/paste the following to download the data: `wget -O flankerData_n4_FA25.tar.gz https://osf.io/gzc2a/download`
*  unpack the download by copy/pasting this in your terminal: `tar -zxvf flankerData_n4_FA25.tar.gz`
*  type `ls` and you should now see you have a new folder named: `flankerData_n4`
*  the contents of this folder include four sub-folders for subjects sub-001, sub-002, sub-003, sub-004 <br/>