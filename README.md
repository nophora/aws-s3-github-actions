# AWS S3 GitHub Actions Deployment.  

## Build and deploys a JavaScript app to AWS S3.  

The `.github/workflows/production.yml` script is specifically for a React app (using TypeScript) and may be adapted for other JS apps.  

Includes React-based environment variables `process.env.REACT_APP_API` to connect to an API service as an example.  

Environment variables must exist in GitHub Secrets.  AWS IAM permission will need to have `AmazonS3FullAccess` permissions enabled to work.  

This script uploads all asset files before uploading the `index.html` file.

![GitHub Secrets must exist](https://www.aaronwht.com/images/tutorial/github-secrets.png)  
