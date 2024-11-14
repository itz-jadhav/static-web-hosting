# Static Website Deployment with AWS CodePipeline, S3, and CloudFront #

This project sets up continuous integration and deployment for a static website using AWS CodePipeline, S3 for storage, CloudFront as the CDN, and GitHub as the source repository.

Setup Instructions

1.Create an S3 Bucket

. Go to the S3 console in AWS.

-Create a new bucket with a unique name (e.g., my-static-website-bucket).

![image](https://github.com/user-attachments/assets/259d0251-4292-4c7b-a7e1-8da00311d779)


-Upload a html file in my-static-website-bucket.

![image](https://github.com/user-attachments/assets/ad59acc2-40af-49c6-9346-4c42e7607f39)



-Enable "Static website hosting" in the properties of the bucket

![image](https://github.com/user-attachments/assets/5b970a63-538a-4ea8-80d5-db6be2b7239e)



Set Up CloudFront

-In the CloudFront console, create a new CloudFront distribution.

![image](https://github.com/user-attachments/assets/85dd6b69-6c87-48fe-ae8f-43fc28e37391)


-Set the origin to your S3 bucket.

![image](https://github.com/user-attachments/assets/c734c5e8-79b0-40a1-b994-90da9d5104ca)


-Configure the default cache behavior settings as needed.

-Set the appropriate bucket policy to allow public read access to the content (adjust if using CloudFront signed URLs). 

![image](https://github.com/user-attachments/assets/007550cd-5308-45f8-ba96-f5d7c99ff1e4)


-Check the CloudFront distribution URL.

![image](https://github.com/user-attachments/assets/ce1fc70b-20a8-461b-83bf-7a867e1ded40)


Connect GitHub Repository to CodePipeline Go to the CodePipeline console.

![image](https://github.com/user-attachments/assets/9049ab35-b317-4299-a4f3-cc83c55244fe)


-Create a new pipeline and select GitHub as the source provider.

![image](https://github.com/user-attachments/assets/170b78dc-5d4a-4d39-9d81-2760f8f02969)


-Authenticate with GitHub and select the repository and branch for the website.

![image](https://github.com/user-attachments/assets/faf9699c-2659-4985-adb1-f7e748a840a5)


-Add an S3 bucket as the deployment destination.

![image](https://github.com/user-attachments/assets/ad866548-994c-4b8a-a9ff-262d90bb7ff3)


-Add S3 as the Deployment Provider

-In CodePipeline, add an S3 bucket as the deployment provider.

-Point it to the previously created S3 bucket.

-Deploy and Verify

![image](https://github.com/user-attachments/assets/9fc0274e-668c-4dbd-9205-78af6e727394)


-Commit changes to the GitHub repository.

![image](https://github.com/user-attachments/assets/01ea0636-583b-47af-a81a-a823179bcfc0)


-CodePipeline will automatically start and deploy the site to the S3 bucket.

-Access the deployed website through the CloudFront distribution URL.

![Screenshot 2024-11-14 212713](https://github.com/user-attachments/assets/62a2c1a8-a0fc-4a12-b0d9-a7536310b04b)


CloudFront caching may delay changes; you can invalidate the cache if needed.

