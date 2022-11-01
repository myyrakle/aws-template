VPC에 람다를 추가할 경우 아래 오류가 발생할 수 있음

```
The provided execution role does not have permissions to call CreateNetworkInterface on EC2
```


아래 형태의 정책을 생성해서 권한에 추가할 필요 있음
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeNetworkInterfaces",
        "ec2:CreateNetworkInterface",
        "ec2:DeleteNetworkInterface",
        "ec2:DescribeInstances",
        "ec2:AttachNetworkInterface"
      ],
      "Resource": "*"
    }
  ]
}
```
