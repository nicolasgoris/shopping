# Shopping
UI5 shopping app created in the SAP BAS from project template.

## Getting started in the SAP BAS
### Git repository
Use the BAS to import the project with the following steps:
* Open menu 'Help' and choose for 'Welcome Page'.
* Click on 'Clone from Git'.
* Enter the URL of this git repository.
* This will clone the git repository in your BAS.
### Create from project template
Use the BAS and create a new project from a template with the following steps:
* Open menu 'File' and choose for 'New Project From Template'.
* Choose for the 'SAP Fiori Freestyle Project' template.
* Choose 'ABAP' as your environment and choose the 'SAP Fiori Master-Detail Application' as template.
* Provide a project name (e.g. 'shopping') and choose an appropriate namespace (e.g. 'be.ap').
* Provide a title (e.g. 'Shopping'), a description (optional) and choose for 'Standalone App'.
* Choose 'My SAP systems' as your system, choose 'r36z' as your source and choose your service (e.g. 'ZSD_00_SHOPPING_SRV').
* Choose the appropriate parameters for the different fields on the screen from your Object Collection.
* This will generate the project.

## Running the app
* Go to the 'Run Configurations' tab on the left.
* Create a new configuration.
* Choose your project (e.g. 'shopping').
* Choose the 'index.html' file as your runnable file.
* Choose the latest UI5 version.
* Choose your configuration name, default is ok.
* Open your configuration and check the 'Data Source', it will link to 'r36z' but will not be binded yet.
* Bind by clicking on the 'Bind' icon on the right.
* Choose 'r36z' as the destination.
* Click on the 'Run Module' icon.
* Wait untill you see a message stating that a service is listening.
* Click on the 'Open in New Tab' button.
* This should open the app in a new tab and you can test out the app.

## Deploy the app
* Open a new terminal via the menu 'Terminal'.
* Execute the command 'npm i', this will install the npm packages.
* Execute the command 'npm run build', this will execute the build process of the UI5 app. Be advised that this will execute the following command: ui5 build --include-task=generateManifestBundle generateCachebusterInfo
* Execute the command 'abap-deploy', this will trigger the deploy process and request several parameters.
  * Provide the source folder: './dist'.
  * Provide the target system: 'r36z'.
  * Provide an application name, this must start with 'ZSD': e.g. 'ZSD_00_SHOPPING'.
  * Provide a description: e.g. 'Shopping app'.
  * Provide the package for the application: e.g. 'ZSD_000_EXAMPLES'.
  * Provide a transport request for the application: e.g. 'R36KXXXXXX'.
* Wait patiently until the app is deployed.
* Open a new browser tab and paste the following url: 'https://r36z.ucc.ovgu.de/sap/bc/ui5_ui5/sap/[placeholder]/index.html?sap-client=201'.
* Replace the placeholder with your application name, results in e.g. 'https://r36z.ucc.ovgu.de/sap/bc/ui5_ui5/sap/zsd_00_shopping/index.html?sap-client=201'.
* If your app loads, be happy and smile!