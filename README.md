# Serverless Image Processing with AWS Lambda and S3

## Project Overview

This project implements a simple serverless image processing workflow using AWS services. Users upload an image to an S3 input bucket, which triggers a Lambda function to process the image (e.g., resizing). The processed image is stored in another S3 output bucket and made accessible via CloudFront.

---

## Architecture Diagram

![Architecture](architecture.png)

---

## AWS Services Used

- **Amazon S3**: For storing input and output images.
- **AWS Lambda**: For serverless image processing.
- **Amazon API Gateway**: To upload images via HTTP request.
- **Amazon CloudFront**: To distribute processed images globally via CDN.
- **Amazon CloudWatch**: For logging and monitoring.
- **IAM**: To securely manage access permissions.

---

## How It Works

1. The user uploads an image through API Gateway.
2. The image is stored in the S3 input bucket.
3. An S3 trigger invokes the Lambda function.
4. Lambda processes the image (e.g., resizes it).
5. The result is stored in the output S3 bucket.
6. The processed image is accessed via CloudFront.

---

## Setup Instructions

### Prerequisites

- An active AWS account.
- IAM role with permissions for S3, Lambda, and CloudWatch.
- Python 3 installed locally.
- [Pillow](https://pypi.org/project/Pillow/) library installed.

### Steps

1. Create two S3 buckets:
   - `input-bucket` (for original images)
   - `output-bucket` (for processed images)
2. Write the Lambda function using Python and Pillow.
3. Package the Lambda function and dependencies into a `.zip` file.
4. Deploy the Lambda and configure it with an S3 trigger.
5. Set up API Gateway to receive uploads and put images in the input bucket.
6. Configure CloudFront to serve files from the output bucket.
7. Use CloudWatch to monitor Lambda execution and logs.

---

## Security

- Use IAM roles with least privilege for Lambda access.
- Apply bucket policies to restrict access to S3 buckets.
- Enable logging in CloudWatch for auditing and debugging.

---

## Cost Optimization

- Uses only serverless and pay-per-use AWS services (S3, Lambda, API Gateway).
- Eligible for AWS Free Tier for most usage levels.

---

## Learning Outcomes

- Build a complete serverless application using AWS.
- Understand event-driven architecture with S3 triggers and Lambda.
- Implement secure and scalable storage with S3 and delivery with CloudFront.
- Learn how to monitor and troubleshoot using CloudWatch.
