# auto-deploy-rstudio-connect

Example use of the RStudio Connect APIs for automated deployment of Shiny app updates
to an instance of RStudio Connect.

## Contents

### `shiny-app/` project folder

Contains a simple Shiny app and a `manifest.json` for the project that was generated
using the following command in the R console:

```
rsconnect::writeManifest()
```

### `.travis.yml

Configuration file used by Travis CI that contains environment variables when the CI job runs:

* `APP_GUID` for the app deployed in RStudio Connect
* `CONNECT_SERVER` for the RStudio Connect server address
* A secure environment variable that contains the RStudio Connect user API key

And a script that runs the `upload_and_deploy.sh` deployment script

### `upload_and_deploy.sh` deployment script

Script that deploys updates to the application when invoked from the CI job.
