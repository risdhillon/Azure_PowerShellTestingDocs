# Azure_PowerShellTestingDocs

One of the main advantages of PowerShell in Cloud Shell is that it makes management of your Azure Resources strikingly easy. In this tutorial, we’ll take you through saving a git repository locally into your Azure CloudDrive, and deploying a website in this repository to AzureSites – all through using the CLI interface for PowerShell in Cloud Shell. Additionally, we’ll show you how easy it is to make changes to your site all within the PowerShell in Cloud Shell browser (using vim). This allows you to fluidly manage editing your web apps and redploying them, within just a few minutes.   

## Deploying a Web App to Azure Hosting using PowerShell in Cloud Shell
Open up Powershell in Cloud Shell in portal.azure.com (sign up for the PowerShell in Cloud Shell preview [here](https://blogs.msdn.microsoft.com/powershell/2017/05/23/coming-soon-powershell-in-azure-cloud-shell/).) 

![alt text](https://github.com/risdhillon/Azure_PowerShellTestingDocs/blob/master/images/open1.PNG)
Clicking the Cloud Shell icon (red arrow above) will launch PowerShell in Cloud Shell. If you haven't already, you may need to initialize Cloud Storage and mount to clouddrive (as shown [here](https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart)). 


Then perform the following steps: 

1.	Git clone your public github repository into your $HOME directory: 

        ```cd $HOME
        cd CloudDrive 
        git clone <YOUR REPOSITORY HERE>```
        
  For example, you can git clone this very [example repo](https://github.com/risdhillon/Azure_PowerShellTestingDocs): https://github.com/risdhillon/Azure_PowerShellTestingDocs. 

2. Navigate to your cloned directory:
  
         ```cd <YOUR CLONED GIT FOLDER>```

3. Within the cloned directory, follow along the existing documentation on deploying from a local git repo, available [here](https://docs.microsoft.com/en-us/azure/app-service-web/scripts/app-service-powershell-deploy-local-git). Note that only 10 free tiered resource groups can be made in a subscription, so please be aware of that as you attempt to create new web apps in a certain subscription. 

## Fluidly Updating Your Web App through PowerShell in Cloud Shell
You can quickly and easily make changes to your site in browser via PowerShell in Cloud Shell. For example. Let’s say we want to remove and change the text on this deployed website – we can do so by using vim and editing the specific file of interest as below

1. Navigate to your cloned github repo in your cloud drive. 
2. Open up the file that you wish to edit with vim. In this example, we will edit the index.html file:
```vim index.html```

3. Edit the file as you wish (note that in vim, you can use i for insert and :wq to write and quit when you are done). 
4. Add all files:
'''git add --all'''
Note that if you get an error message asking you to configure your github account, please do so. 
5. Commit all your files and changes
``` Git commit -am 'changed index.html' ```
6. Git push azure master
7. Navigate to the website address <YOUR WEBSITE NAME>.azuresites.net to see the live site. 
