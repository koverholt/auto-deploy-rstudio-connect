# auto-deploy-rstudio-connect

This example Shiny app and manifest can be deployed to RStudio Connect using the
[Git-backed deployment functionality](https://blog.rstudio.com/2019/06/24/rstudio-connect-1-7-6/).
RStudio Connect will handle the initial deployment from Git as well as updates
to the Shiny app as they are pushed to this repository.

## Configuration steps

1. Fork this repository
2. From RStudio Connect, select the option to `Publish > Import from Git`
3. Point to the Git URL of your forked repository and continue with the configuration
4. The Shiny app will then be deployed to RStudio Connect
5. Make a change to the Shiny app and commit the change to Git
6. RStudio Connect will poll the repository for changes then deploy the updated version of the Shiny app
7. Repeat Step 5 to customize the app, and enjoy automated re-deployments of your Shiny app!

## Contents

### `shiny-app/` project folder

Contains a Shiny app (`app.R`) and a `manifest.json` for the project that was
generated using the following command in the R console:

```
rsconnect::writeManifest()
```

## Looking for programmatic CI/CD deployments?

Refer to the [Deploying with APIs](https://github.com/rstudio/connect-api-deploy-shiny)
example for more information on fully customizable programmatic deployments that
make use of the deployment APIs in RStudio Connect and CI/CD systems.
