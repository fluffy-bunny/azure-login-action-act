# azure-login-action-act

Trying to get this to work with [github.com/nektos/act](https://github.com/nektos/act).  

## Steps
### One  
The same credentials that I added in `"project->settings->secrets"`;  
[github.com/Azure/login](https://github.com/Azure/login)  

```
AZURE_CREDENTIALS={}
```
This works when running on the github cloud;

### Two  
Locally I put the same AZURE_CREDENTIALS as an environment variable.  
```bash
export AZURE_CREDENTIALS=`{}`
```
### Three 
Run act locally
```bash
act -s AZURE_CREDENTIALS
```  
 

