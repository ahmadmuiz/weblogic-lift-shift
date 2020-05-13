# Oracle WebLogic Server Installation on OCI Guide

## Pre-requisite

This guide assumes you have already provisioned OEL Compute on OCI and have SSH access to the environment

## Step 1: Download WebLogic Server Binary

- Secure Shell into OCI compute and login as opc, you should not need to enter password since we are using the generated private key
- Create a new directory under opc home called 'install', this folder should be accessable from /home/opc/install. (mkdir install)  

![Screenshot 1](images/weblogic_install/screenshot1.jpg)  

- Download the generic installer for WebLogic Server 14c from https://www.oracle.com/middleware/technologies/fusionmiddleware-downloads.html, and put the file fmw_14.1.1.0.0_wls_Disk1_1of1.zip into the install folder as shown below:  

![Screenshot 2](images/weblogic_install/screenshot2.jpg)  

## Step 2: Install Java

You can check the available JDK with the command: yum list jdk*, a sample output is as follows:  

![Screenshot 3](images/weblogic_install/screenshot3.jpg)  

We will install JDK 11 here, run the command: sudo yum install jdk-11.0.7  

![Screenshot 4](images/weblogic_install/screenshot4.jpg)  

Once installation complete, you can verify the Java version by running: java -version  

You should be able to see the follow  

![Screenshot 5](images/weblogic_install/screenshot5.jpg)  


## Step 3: Export Display from OCI

Refer to [here](enable_display_in_oci.md)  

## Step 4: Extract WebLogic Installer

From install folder, run command: unzip fmw_14.1.1.0.0_wls_Disk1_1of1.zip (For optimal experience running the installer, provision a Windows compute within the same OCI subnet and run MobaTerm within the Windows server, it's a lot faster)    

![Screenshot 6](images/weblogic_install/screenshot6.jpg)  

Run the install by running command: java -jar fmw_14.1.1.0.0_wls.jar. You should see the follow:  

![Screenshot 8](images/weblogic_install/screenshot8.jpg)  

Enter /home/opc/oraInventory as the inventory directory as follows:  

![Screenshot 9](images/weblogic_install/screenshot9.jpg)  

And click on OK:  

![Screenshot 10](images/weblogic_install/screenshot10.jpg)  

Click 'Next':  

![Screenshot 11](images/weblogic_install/screenshot11.jpg)  

Leave everything as default and click 'Next':  

![Screenshot 12](images/weblogic_install/screenshot12.jpg)  

Accept default home and click 'Next':  

![Screenshot 13](images/weblogic_install/screenshot13.jpg)  

Accept default installation choice and click 'Next'. -Pre-Installation check will start now. Please wait for it to complete:  

![Screenshot 15](images/weblogic_install/screenshot15.jpg)  

Click 'Next' and 'Install' from Summary screen to start the installation process and wait for it to complete:  

![Screenshot 16](images/weblogic_install/screenshot16.jpg)  


Click on 'Finish' to complete the installation.  Now you have WebLogic installed on OCI. You can now proceed to create new domains with Domain Configuration Wizard.  
