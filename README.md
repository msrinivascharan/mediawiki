Containarizing and deploying mediawiki to Kubernetes cluster.

#### Prerequisite 

Installed on Windows 11:   
Docker desktop
Kubernetes single node cluster
Git
Jenkins
helm

#### Steps

CI pipeline created in Jenkins to build Hello World app with below tasks.

1] Checkout
2] Build mediawiki image
3] Publish mediawiki image to Docker hub
4] Build mariadb image
5] Publish mariadb image to Docker hub
6] Installing mariadb and Mediawiki using helm chart by providing required inputs
7] Open http://localhost: to see mediawiki home page, you can login with admin credentials and create wiki pages

Note:
Issues, WIP
1] Mariadb image created from custom Dockerfile not working, issue with entrypoint script
2] Media wiki Deployed through helmcharts(install.sh script) not showing rich UI
3] Mediawiki deployed directly on k8s working fine without any issues
