

```PowerShell
get-launch-template-data
create-launch-template-version
modify-launch-template
describe-launch-template-versions
delete-launch-template-versions

___________________________________________________________

create-launch-template

aws ec2 create-launch-template \
    --launch-template-name TemplateForWebServer \
    --version-description WebVersion1 \
    --tag-specifications 'ResourceType=launch-template,Tags=[{Key=purpose,Value=production}]' \
    --launch-template-data file://template-data.json
    
___________________________________________________________

get-launch-template-data

aws ec2 get-launch-template-data \
    --instance-id i-0123d646e8048babc \
    --query "LaunchTemplateData"
    
\\ Print output data to file
    
aws ec2 get-launch-template-data \
    --instance-id i-0123d646e8048babc \
    --query "LaunchTemplateData" >> instance-data.json
    
___________________________________________________________
    
create-launch-template-version
    
aws ec2 create-launch-template-version \
    --launch-template-id lt-0abcd290751193123 \
    --version-description WebVersion2 \
    --source-version 1 \
    --launch-template-data "ImageId=ami-c998b6b2"
    
___________________________________________________________
    
modify-launch-template
    
aws ec2 modify-launch-template \
    --launch-template-id lt-0abcd290751193123 \
    --default-version 2
    
___________________________________________________________
    
describe-launch-template-versions
    
aws ec2 describe-launch-template-versions \
    --launch-template-id lt-0abcd290751193123 \
    --versions 1 3
    
___________________________________________________________
   
describe-launch-template-versions
   
aws ec2 describe-launch-template-versions \
    --versions "$Latest,$Default"
    
___________________________________________________________

delete-launch-template-versions

aws ec2 delete-launch-template-versions \
    --launch-template-id lt-0abcd290751193123 \
    --versions 1
```


```JSON
    
{
    "NetworkInterfaces": [{
        "AssociatePublicIpAddress": true,
        "DeviceIndex": 0,
        "Ipv6AddressCount": 1,
        "SubnetId": "subnet-7b16de0c"
    }],
    "ImageId": "ami-8c1be5f6",
    "InstanceType": "r4.4xlarge",
    "TagSpecifications": [{
        "ResourceType": "instance",
        "Tags": [{
            "Key":"Name",
            "Value":"webserver"
        }]
    }],
    "CpuOptions": {
        "CoreCount":4,
        "ThreadsPerCore":2
    }
}    
```
