# aws-cloudformation-templates
A collections of couldformation-template

The command to make EKS using cloudforatmion 
```bash
aws cloudformation create-stack --region us-west-2 \
  --stack-name eks-$(date +%d%H%M%S) \
  --template-body file://eks.yaml \
  --capabilities CAPABILITY_IAM \
  --parameters \
    ParameterKey="VpcId",ParameterValue="vpc-00000000" \
    ParameterKey="SubnetId",ParameterValue="subnet-ffffffff\\,subnet-ffffffff"
```

The policy that need to run creating stack using cloudformation
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "iam:GetRole",
                "iam:CreateRole",
                "iam:DeleteRole",
                "iam:AttachRolePolicy",
                "iam:PutRolePolicy",
                "ec2:DescribeSecurityGroups",
                "eks:DeleteCluster",
                "iam:PassRole",
                "iam:DetachRolePolicy",
                "cloudformation:CreateStack",
                "iam:DeleteRolePolicy",
                "ec2:DescribeVpcs",
                "ec2:CreateSecurityGroup",
                "ec2:DeleteSecurityGroup",
                "eks:DescribeCluster",
                "ec2:DescribeSubnets",
                "iam:GetRolePolicy",
                "eks:CreateCluster"
            ],
            "Resource": "*"
        }
    ]
}
```
