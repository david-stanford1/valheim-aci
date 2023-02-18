# Valheim Azure ACI Deployment

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdavid-stanford1%2Fvalheim-aci%2Fmain%2Fazuredeploy.json)

Or if you would like to use `az` cli in PowerShell:

``` powershell
az group create --name <resource-group> --location eastus2

az deployment group create --resource-group "<resource-group>" `
    --template-file .\azuredeploy.json `
    --parameters `@azuredeploy.parameters.json `
    --parameters valheimServerPassword yourSuperSecretPassword 

```

This diverges from the base in two ways:
1) I added support for crossplay by adding SERVER_ARGS as well as a flag that lets you make it a public server or not.
2) I removed the regions that my friends and I don't use so it's faster to launch.
