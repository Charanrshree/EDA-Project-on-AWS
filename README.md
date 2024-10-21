# Step-by-Step Guide to Building a EDA Project on AWS

### Project Description:

Let's build a simple event-driven application using AWS services like Amazon S3, AWS Lambda, and Amazon SNS (Simple Notification Service). 

Use Case: Image Upload Notification System \
When an image is uploaded to an S3 bucket, a Lambda function processes the event and sends a notification through SNS.

### Project Architecture:

<img width="1136" alt="Screenshot 2024-06-15 at 2 40 01 PM" src="https://github.com/yeshwanthlm/EDA-Project-on-AWS/assets/66474973/6d3aab89-c68e-4462-81e4-0114fa93e2dd">

### Steps to Build the Project:

* Step 1: Set Up an AWS Account 
* Step 2: Create an S3 Bucket (S3 Bucket Name: amc-eda-project-123) 
* Step 3: Create an SNS Topic (SNS Topic Name: ImageUploadNotification) 
* Step 4: Create a Subscription 
* Step 5: Create a Lambda Function (Lambda Function Name: ImageUploadProcessor) 
* Step 6: Add S3 trigger 
* Step 7: Write Lambda Function Code 
* Step 8: Test the System

**Create a role: s3upload_sns-lambda-role**

1. lamda execution basic with lambda
   
2.  sns full access
   
3.  s3 access below policy
   

                       {
                          "Version": "2012-10-17",
                          "Statement": [
                              {
                                 "Effect": "Allow",
                                 "Action": [
                                    "s3:GetObject",
                                    "s3:PutObject",
                                    "s3:ListBucket"
                                 ],
                                 "Resource": [
                                     "arn:aws:s3:::777777777777777777777",
                                     "arn:aws:s3:::777777777777777777777/*"
                                 ]
                             }
                         ]  
                     }

5. attach all the policies to lamda function in configuration and edit add the role

6. when u create the s3 trigger
 prefix: if u have s3 path name like images/ then only give that name, otherwise leave empty and
   
   suffix: u can leave empty means in root s3 bucket will take and if u have path then give like .jpg if u give this format only, it will consider
   
7. this all above steps i dicovered

### Expected Outcome:

By following these steps, you will have created a simple event-driven application on AWS that demonstrates the core principles of EDA. This setup can be expanded to more complex scenarios as you become more comfortable with the architecture and AWS services. If you need further assistance or have any questions, feel free to ask!

This project will help you improve your skills in cloud computing, serverless architecture, and AWS services.

Link to the video tutorial: 

Follow our tutorials here: https://www.youtube.com/@amonkincloud/videos \
Follow my personal blog here:https://dev.to/yeshwanthlm/ \
Follow us on Instagram: https://www.instagram.com/amonkincloud/ \
For queries write to us at: amonkincloud@gmail.com 



json
Copy code
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::777777777777777777777",
        "arn:aws:s3:::777777777777777777777/*"
      ]
    }
  ]
}
