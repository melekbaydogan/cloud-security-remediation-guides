[![CloudSploit](https://cloudsploit.com/img/logo-new-big-text-100.png "CloudSploit")](https://cloudsploit.com)

# AWS / Firehose / Firehose Delivery Streams Encrypted

## Quick Info

| | |
|-|-|
| **Plugin Title** | Firehose Delivery Streams Encrypted |
| **Cloud** | AWS |
| **Category** | Firehose |
| **Description** | Ensures Firehose Delivery Stream encryption is enabled |
| **More Info** | Data sent through Firehose Delivery Streams can be encrypted using KMS server-side encryption. Existing delivery streams can be modified to add encryption with minimal overhead. |
| **AWS Link** | https://docs.aws.amazon.com/firehose/latest/dev/encryption.html |
| **Recommended Action** | Enable encryption using KMS for all Firehose Delivery Streams. |

## Detailed Remediation Steps
1. Log into the AWS Management Console.
2. Select the "Services" option and search for "Kinesis". </br>![Step 2](/resources/aws/kinesis/kinesis-streams-encrypted/step2.png "Step 2 - Kinesis")
3. Under the "Amazon Kinesis dashboard" choose "Data Firehose" from the left navigation panel. </br>![Step 3](/resources/aws/kinesis/kinesis-streams-encrypted/step3.png "Step 3 - Data Firehose")
4. Select the "Firehose Delivery System" that needs to be verified and click on the "Name" to access the delivery stream.</br>![Step 4](/resources/aws/kinesis/kinesis-streams-encrypted/step4.png "Step 4 - Name") 
5. Select the "Details" tab and scroll down to "Amazon S3 destination". Check the "Encryption" value and if it's set to "Disabled" then the selected "Firehose Delivery System" data is not encrypted. </br>![Step 5](/resources/aws/kinesis/kinesis-streams-encrypted/step5.png "Step 5 - Encryption") 
6. Repeat steps number 4 and 5 to verify another "Firehose Delivery System".</br>
7. To enable the "Encryption" on selected "Firehose Delivery System" click on the "Name" to access the delivery stream. Under the "Details" tab click on the "Edit" button to make the changes in "Amazon S3 destination". </br> ![Step 7](/resources/aws/kinesis/kinesis-streams-encrypted/step7.png "Step 7 - Edit")
8. Click on the "Enable" button next to the "S3 encryption" to enable the encryption. </br>![Step 8](/resources/aws/kinesis/kinesis-streams-encrypted/step8.png "Step 8 - Enable")
9. Choose the "KMS master key" from the dropdown list. Choose either the ("Default( aws/s3 )") KMS key or an AWS KMS Customer Master Key (CMK).</br>![Step 9](/resources/aws/kinesis/kinesis-streams-encrypted/step9.png "Step 9 - KMS Master Key")
10. Click on the "Save" button to make the necessary changes. On the successful configuration changes, one will get "Successfully updated delivery stream" message. </br> ![Step 10](/resources/aws/kinesis/kinesis-streams-encrypted/step10.png "Step 10 - Save")