# Setting up your Visual Studio Codespace environment (VS Code Online)
 
#### Steps

* Navigate to https://online.visualstudio.com/login and click `Sign in` 

    ![codespaces_setup](./assets/codespaces_signin.png)


* You should automatically be redirected to `Codespaces` landing page if you are already signed into the Azure Portal on a different tab.

    * But, if prompted to sign in, make sure to login with the same `outlook / hotmail account` that was used to create the Azure subscription. 

* Click on `Create Codespace` to get started

    ![codespaces_setup](./assets/codespaces_create_plan.png)

* Make sure the correct subscription is selected, and then click `Create` to create your billing plan. This may take a few minutes.

    * This will also create a `Resource Group` for you in selected `Location` (_by default, West Europe_)

    ![codespaces_setup](./assets/codespaces_billing_plan.png)

    * _If you get any error messages such as below, just hit `cancel` and try the above step again after a couple of minutes._

        ![codespaces_setup](./assets/codespaces_known_errors.png)
    
* Once your billing plan is ready, create a new codespace. 

    * Give it a name of your choice and set the suspend idle timeout to `2 hours`. Codespace will auto suspend after 2 hours to help with cost savings.

    ![codespaces_setup](./assets/codespaces_create.png)  

* It may take a couple of minutes to `Initialize the codespace`. 

    * Once it's initialized, you should see your `codespace environment` (vs code on the cloud) such as below and you're all set to go. 

    ![codespaces_setup](./assets/codespaces_complete.png)  

* If you are new to `vs code`, take a few minutes to familiarzie yourself with the IDE. Here is a quick overview.

    ![codespaces_setup](./assets/vs_code_overview.png)    

* To connect back to your codespaces environment, just go to https://online.visualstudio.com/environments and connect to your environment as shown below.

    ![codespaces_setup](./assets/codespaces_reconnect.png) 

* If you're interested to know / learn more about vs code, see: https://code.visualstudio.com/docs/getstarted/tips-and-tricks 