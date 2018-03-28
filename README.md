# This template can be used to spin up a machine in an existing management VPC/subnet
# jenkins-cloudformation-template.json - this template can be used to spin up Launch configuration with user data, Esecurity groups and dns

# Precondition: 
# You should have working management VPC and subnet which can be passed as parameter in order to create jenkins master machine
# You should own valid domain name

#Required parameters
# Provide below parameters in jenkins-cloudformation-template.json
* AvailabilityZone - Availability Zone
  Example: eu-west-1b
* InstanceType - Instance type
  Example: t2-small
* EBSVolumeID - 'create', or an existing EBS volume ID to use instead of creating a new one.
  Example: create
* EBSVolumeSize - The size of the EBS volume to create (in GB), if EBSVolumeID is set to 'create'
  Example: 120
* ENV - Environment name which will be used as prefix for all the resources
  Example: <project specific name> or any name you want to prefix all the resources with
* KeyNameTest - Name of an existing EC2 KeyPair to enable SSH access to the instances
  Example: Any valid keypair which you want to use and you have access
* AMI - Latest AMI for ubuntu ami from marketplace
  Example: ami-XXXX
* MyServiceVPC - VPC with some useful service tools
  Example: vpc-XXXX
* ELBSecurityGroup - Access to ELBs from port 443 vpn address range
  Example: sg-XXXX
* SSHSGFromJmpHost - Allow SSH connection from jump host
  Example: sg-XXXX (choose the required sg in your environment)
* ACMIdentifier - Identifier of ACM certificate which will be used for LB
* Subnetpri1a - Private subnet eu-west-1a
  Example: subnet-XXXX
* Subnetpri1b - Private subnet eu-west-1b
  Example: subnet-XXXX
* Subnetpri1c - Private subnet eu-west-1c
  Example: subnet-XXXX
* DnsZone - Use valid DnsZone
* HostedZoneId - HostedZone for the Private Domain
* RegionPrefix - AWS region. e.g. dub for dublin, ore for oregon. This is used to prefix the backup bucket
  Example: dub-jenkins-backup

