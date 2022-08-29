# Automate_S3_Using_Python
Creating S3 bucket and uploding files to it by using boto3 module with the help of Python....<br><br>
**AWS Configure :**
<br>
( enter your aws access key id,<br>
aws secret access key,<br>
region name(ap-south-1),<br>
output format(json) )<br>

### creating S3 bucket :
```
import boto3   #import boto3
resource = boto3.resource('s3')   #select resource (s3)
bucket = resource.Bucket("new-bucket-name") #giving name to the bucket.
bucket_properties = bucket.create(
    ACL='private',
    CreateBucketConfiguration={'LocationConstraint':'eu-central-1'}
)

print(bucket_properties)
print("Bucket created successfully......!")
```
### Uploading file to S3 bucket.
```
import boto3
resource = boto3.client('s3')
resource.upload_file(
    Filename='file_1.png',
    Bucket='Bucket_Name',
    key='save_1.png'
)
print("File Uploaded to your S3 Bucket Successfully")
```



