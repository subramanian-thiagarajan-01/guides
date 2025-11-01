## Connect to Azure Key Vault from Databricks

1. Create an Access Connector in Azure
Provision a Managed Identity Access Connector for your Databricks workspace in Azure. This acts as a secure bridge between Databricks and Key Vault.​

2. Assign Key Vault Permissions
In your Azure Key Vault, use IAM (Access Control) to assign the "Key Vault Secrets User" role to the Access Connector managed identity.​

3. Set Up Unity Catalog Service Credential
In Databricks, go to Unity Catalog > Credentials and create a new Service Credential.

Paste the Resource ID of the Azure Access Connector.

Specify which users, service principals, or groups in Databricks can use this service credential for accessing the Key Vault.​

4. Access Key Vault from Databricks Notebook
Install the required Azure SDK library in your cluster or notebook environment:

```
%pip install azure-keyvault-secrets
```
Use the following Python code pattern:

```python
from azure.keyvault.secrets import SecretClient

credential = dbutils.credentials.getServiceCredentialsProvider('your-service-credential-name')
vault_url = "https://<your-keyvault-name>.vault.azure.net/"
client = SecretClient(vault_url=vault_url, credential=credential)
secret_value = client.get_secret("<your-secret-name>").value
print(secret_value)
```
Replace 'your-service-credential-name' with the name of the credential you created in Unity Catalog, and <your-keyvault-name> and <your-secret-name> as appropriate.
