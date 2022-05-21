# Setup Jupyter Notebook on Azure via SSH

## Sign in to Azure
Sign in to the [Azure portal](https://portal.azure.com/).

## Create virtual machine
* Enter virtual machines in the search or click Virtual machines under Azure services. 

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p>

  Under Services, select Virtual machines.

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p>

* In the Virtual machines page, select Create and then Azure Virtual machine. 

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p>

  The Create a virtual machine page opens.

* In the Basics tab, under Project details, make sure the correct subscription is 
  selected and then choose to Create new resource group. Enter <name-of-your-choice> for the name.
  mlops will be used in this tutorial
  
<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p>
  
* Under Instance details, enter azurevm for the Virtual machine name, and choose Ubuntu 20.04 LTS - Gen2 for your Image. 
  Leave the other defaults. The default size and pricing is only shown as an example. 
  Size availability and pricing are dependent on your region and subscription.
  The Standard_E2s_v3 - 2 vcpus, 16 GiB memory will be used in this tutorial

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p>  
 
* Set Authentication type to 'SSH public key'

  Set Username, Generate new key pair and set key pair name.

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p> 
 
* Set Inbound port rules
  Allow selected ports and select 'HTTP (80)' and 'SSH (22)'
  
  Leave the remaining defaults and then select the Review + create button at the bottom of the page.
 
* It will take you to a service pricing webpage. Go through it. 
  When you are ready, select Create.

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p> 
  
* When the Generate new key pair window opens, select Download private key and create resource. 
  Your key file will be download as azurevmkey.pem. Make sure you know where the .pem file was downloaded; 
  you will need the path to it in the next step.

<p align=center>
<img src="https://github.com/josepholaide/examples/blob/master/jpx-tokyo-stock-exchange-kaggle-competition/images/kaggle-click-account.PNG?raw=true" alt="enter username" width="900" height="300"/>
</p> 

## Connect to virtual machine
Create an SSH connection with the VM.

If you are on a Mac or Linux machine, open a Bash prompt. 
If you are on a Windows machine, you can use a PowerShell prompt but in this tutorial, we will use git bash.

At your prompt, open an SSH connection to your virtual machine. Replace the IP address with the one from your VM, and replace 
the path to the .pem with the path to where the key file was downloaded.

`ssh -i .\<pem-directory>\azurevmkey.pem azureuser@20.106.112.123`
  
  
## Step 1: Download and install the Anaconda distribution of Python
`wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh
bash Anaconda3-2022.05-Linux-x86_64.sh`
  
 
