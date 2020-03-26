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
Output..  
```
$ act -s AZURE_CREDENTIALS
[Azure Login Test Locally/Azure-Login] 🚀  Start image=node:12.6-buster-slim
[Azure Login Test Locally/Azure-Login]   🐳  docker run image=node:12.6-buster-slim entrypoint=["/usr/bin/tail" "-f" "/dev/null"] cmd=[]
[Azure Login Test Locally/Azure-Login] ⭐  Run az login
[Azure Login Test Locally/Azure-Login]   ☁  git clone 'https://github.com/azure/login' # ref=v1
[Azure Login Test Locally/Azure-Login]   🐳  docker cp src=/home/ghstahl/.cache/act/azure-login@v1 dst=/actions/
[Azure Login Test Locally/Azure-Login]   ⚙  ::set-env:: AZURE_HTTP_USER_AGENT=GITHUBACTIONS_AzureLogin_267628c931a3d62511b4c3247de1d664565d2186161c53732a4b56e1dd7cac9e
[Azure Login Test Locally/Azure-Login]   ❗  ::error::Login failed. Please check the credentials. For more information refer https://aka.ms/create-secrets-for-GitHub-workflows
[Azure Login Test Locally/Azure-Login]   ❗  ::error::Error: Unable to locate executable file: az. Please verify either the file path exists or the file can be found within a directory specified by the PATH environment variable. Also check the file mode to verify the file is executable.
[Azure Login Test Locally/Azure-Login]   ⚙  ::set-env:: AZURE_HTTP_USER_AGENT=
[Azure Login Test Locally/Azure-Login]   ❌  Failure - az login
```

