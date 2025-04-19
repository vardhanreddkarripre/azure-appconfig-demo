Prerequisites: 

1. Fork the below repo
Github Repo link:
https://github.com/ibnehussain/azure-appconfig-demo.git
2. Admin access to create Managed Identity

Lab: 
Step 1: Create an Azure App Configuration Store
•	Go to the Azure Portal.
•	Search for "App Configuration" → Click "Create".
•	Fill in details (Resource Group, Name, Location) → Create.
•	Once created, go to "Configuration Explorer" and add these key-value pairs:

PromoBanner/Text: "Summer Sale - 50% Off!"
PromoBanner/Color: "blue" (or any CSS color like "#FF5733")
Feature/NewCheckout: "true"

Step 2: Set Up Azure Key Vault
•	Create a Key Vault:
•	Go to Azure Portal
•	Search for "Key Vault" → Create
•	Fill in details (Name, Resource Group, Region)
•	Click "Review + create" → Create
•	Add your App Configuration connection string as a secret:
•	Go to your new Key Vault → "Secrets" → "Generate/Import"
•	Name: AppConfigConnectionString
•	Value: Paste your App Configuration connection string
•	Click "Create"


Step 3: Deploy Azure App Service
Create an Azure Web app with stack as Node 20 LTS

Step 4: Configure Azure App Service
Enable Managed Identity:

Go to your App Service → "Identity"
Turn on "System assigned" identity → Save

Step 5: Grant key vault access to Identity
Go to your Key Vault → "Access control (IAM)"
Click "Add role assignment"
Select role: "Key Vault Secrets User"
Assign access to: "Managed identity"
Select your App Service's identity
Click "Review + assign"






Step 6 : Update app.js to use Key Vault:

// Key Vault URL (replace with yours)
const keyVaultUrl = "https://YOUR-KEYVAULT-NAME.vault.azure.net";
 ![image](https://github.com/user-attachments/assets/c2400358-07d2-421a-b285-31f36a1e9214)

Step 7: Add GitHub as source in your Azure App settings
Go to Deployment center and add the forked repo.

