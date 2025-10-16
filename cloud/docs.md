### Ref https://docs.ansible.com/ansible/2.9/modules/list_of_cloud_modules.html

### For accessing the AWS Account, you need to
1. export AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_REGION
     or
2. You can configure profile using aws configure (cli)
     or
3. You can configure profile (\~/.aws/config_filename) as under if running from ec2 instance, it will assume the role provided your instance profile(IAM associated with ec2) has assume role capabilities and the target role trusts IAM assocaited with ec2
                  <pre>
                     \[profile dev\]
                     role_arn=arn:aws:iam::accid:role/role-name
                     region=eu-west-1
                     credential_source=Ec2InstanceMetadata
                     metadata_service_timeout=5
                     metadata_service_num_attempts=5
                  </pre>
   export AWS_CONFIG_FILE=~/.aws/config_filename
   export AWS_DEFAULT_PROFILE=dev
