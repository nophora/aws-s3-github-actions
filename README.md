# AWS S3 GitHub Actions Deployment

## Builds and deploys a JavaScript app to AWS S3.

The `.github/workflows/production.yml` script is specifically designed for a React app (using TypeScript) and may be adapted for other JS apps.

This script uploads all asset files (JS, CSS, images, woff, etc), then uploads the `index.html` file before invalidating the CloudFront cache for `/index.html`.

Includes React-based environment variables `process.env.REACT_APP_API` to connect to an API service as an example.

Environment variables must exist in GitHub Secrets.

AWS IAM permission for `AWS_ACCESS_KEY_ID` needs to have `AmazonS3FullAccess` enabled, along with a custom policy (example below) to invalide a CloudFront Cache:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "cloudfront:CreateInvalidation",
            "Resource": "arn:aws:cloudfront::XXXXXXXXXXXX:distribution/XXXXXXXXXXXXX"
        }
    ]
}
```

![GitHub Secrets must exist](https://www.aaronwht.com/images/tutorial/github-actions-secrets.png)
