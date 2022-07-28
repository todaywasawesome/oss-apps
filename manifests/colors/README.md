# Colors Application
App repo: https://github.com/todaywasawesome/color-coded

# Promoting changes from staging to production. 
The manifest folder uses a sub-folder for each application to be managed with additional subfolders for each environment. 
* base - Contains all the manfiests needed to deploy an application. 
* staging - Contains a kustomization overlay with a patch for staging and then overrides that normally go with releases.
* production - Contains the same as staging with a different specific overlay for prod. 

To release a change, first update the staging kustomization. After a successful rollout and test, make the same changes to the production version.

# Using Helm
The base folder may contain a Helm chart. The overlays may reference this Helm chart or an external Helm chart with a specific version. 