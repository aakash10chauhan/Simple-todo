Simple-todo
----------------------------------------------------------------------------------------------------------------------------------------------------
This is a simple jenkins pipeline which deploys a basic html static web application to AWS S3 bucket
This pipeline checks if aws S3 bucket dosent exists then creates a bucket through AWS CLI with S3 module and copies all the files in the S3 bucket.
