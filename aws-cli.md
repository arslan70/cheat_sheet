# AWS CLI COMMANDS
## EC2
### Get Image of instance-id
aws --profile <profile>  ec2 describe-images --image-ids $(aws --profile <profile> ec2 describe-instances --instance-ids <instance-id> --query 'Reservations[0].Instances[0].ImageId' --output text  --region <region>) --query 'Images[0].Name'  --region <region>

## Dynamo DB
### Update Item
 aws --profile dev dynamodb update-item  --table-name terraform_locks --key '{"LockID":{"S":"restcomm-cluster-dev/infra/dev-us-restcomm-md5"}}' --attribute-updates '{"Digest": {"Action": "PUT","Value":{"S":"9189aae4d18098f7f8255cf539c65a4a"}}}'

