# AWS S3 GitHub Actions Deployment. 

Build and deploys a JavaScript app to AWS S3.  

This version of the script is specifically for a React app (using TypeScript) and could also be used for other JS apps.

Environment variables must exist in GitHub Secrets.

This script initially uploads all files but the `index.html`, then uploads the `index.html` file.

![GitHub Secrets must exist](https://www.aaronwht.com/images/tutorial/github-secrets.png)  
