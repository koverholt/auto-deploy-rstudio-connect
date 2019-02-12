# auto-deploy-rstudio-connect

Example use of the RStudio Connect APIs for automated deployment of Shiny app updates
to an instance of RStudio Connect.

## Configuration steps

1. Fork this repository
2. Deploy the Shiny app to RStudio Connect
3. Input the address of the RStudio Connect server as an environment variable in `.travis.yml`
4. Input the GUID for the Shiny app as an environment variable in `.travis.yml`
5. Input your RStudio Connect API key as an encrypted environment variable in `.travis.yml`
6. Activate Travis CI for the Git repository
7. Make a change to the Shiny app and commit the change to Git
8. The CI job will deploy the updated version of the Shiny app to RStudio Connect
9. Repeat Step 7 to customize the app as much as you'd like, and enjoy automated re-deployments of your Shiny app!

## Contents

### `shiny-app/` project folder

Contains a Shiny app and a `manifest.json` for the project that was generated
using the following command in the R console:

```
rsconnect::writeManifest()
```

### `.travis.yml` configuration file

Configuration file used by Travis CI that contains environment variables when the CI job runs:

* `APP_GUID` for the app deployed in RStudio Connect
* `CONNECT_SERVER` for the RStudio Connect server address
* A secure environment variable that contains the RStudio Connect user API key

And a script that runs the `upload_and_deploy.sh` deployment script

### `upload_and_deploy.sh` deployment script

Script that deploys updates of the application to RStudio Connect when invoked from the CI job.
