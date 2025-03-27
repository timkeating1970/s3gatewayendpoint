# s3gatewayendpoint

This template includes:

Parameters:

BucketName: The S3 bucket name [1]

VpcId: The VPC where the endpoint will be created

RouteTableId: The route table to associate with the endpoint

Resources:

S3GatewayEndpoint: Creates the VPC endpoint for S3 with a policy that allows specific S3 actions

EC2InstanceRole: IAM role for EC2 instances with permissions to access S3 only through the VPC endpoint

EC2InstanceProfile: Instance profile to attach the role to EC2 instances

S3BucketPolicy: Bucket policy that denies access unless it comes through the VPC endpoint

Outputs:

VPCEndpointId: The ID of the created VPC endpoint

EC2InstanceProfileArn: The ARN of the instance profile to attach to EC2 instances

To use this template:

The S3 bucket must exist before deploying this template

You'll need to provide the VPC ID and Route Table ID

The EC2 instances must be launched with the created instance profile to access the S3 bucket

The bucket policy ensures that access is only allowed through the VPC endpoint

The template implements security best practices by:

Restricting S3 access to only through the VPC endpoint

Using least privilege permissions in IAM roles

Including SSM managed policy for instance management

Implementing condition checks in both IAM and bucket policies