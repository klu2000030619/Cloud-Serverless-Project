# Serverless Speech-to-Text with AWS Transcribe and S3 Event Trigger using Lambda and CloudWatch
This experiment demonstrates how to use AWS services to convert speech from an audio file to text using AWS Transcribe and S3 Event Trigger with Lambda and CloudWatch.

## Prerequisites
Before starting, you will need:
* An AWS account
* Basic knowledge of AWS services like S3, Lambda, and CloudWatch


## How to run the experiment
To run this experiment, follow these steps:
1. Clone or download the GitHub repository containing the source code for the project.
2. Navigate to the speech-to-text-lambda folder in the project.
3. Create an S3 bucket in your AWS account if you haven't already done so.
4. Upload an audio file to the S3 bucket you just created.
5. Open the AWS Management Console and navigate to the Lambda service.
6. Click on the "Create function" button.
7. Choose "Author from scratch", give your function a name, select "Python 3.7" as the runtime   and choose an existing role or create a new one.
8. Click "Create function".
9. In the "Function code" section, copy the code from the lambda_function.py file in the repository and paste it into the code editor.
10. Replace the BUCKET_NAME variable value with the name of the S3 bucket you created in step 3.
11. Click on the "Deploy" button.
12. Navigate to the S3 service and select the bucket you created in step 3.
13. Click on the "Properties" tab and then click on the "Events" button.
14. Click on the "Add notification" button and configure the S3 event trigger as follows:
    * Event type: "All object create events"
    * Prefix: leave this field blank
    * Suffix: ".mp3" (replace with the file extension of your audio file)
    * Send to: "Lambda function"
    * Lambda function: select the Lambda function you created in step 7
    * Click on "Save"
15. Once the transcription job is complete, you can view the transcribed text in the AWS Transcribe console.

## Conclusion
In this experiment, we've demonstrated how to use AWS Transcribe and S3 Event Trigger with Lambda and CloudWatch to convert speech from an audio file to text. This could be useful for a variety of applications, such as transcribing lectures, podcasts, or interviews.
