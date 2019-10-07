# AWS CLI COMMANDS
## Describe instance
### Get Image of instance-id
aws --profile <profile>  ec2 describe-images --image-ids $(aws --profile <profile> ec2 describe-instances --instance-ids <instance-id> --query 'Reservations[0].Instances[0].ImageId' --output text  --region <region>) --query 'Images[0].Name'  --region <region>
