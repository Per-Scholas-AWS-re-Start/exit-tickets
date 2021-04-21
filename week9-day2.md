Exit Ticket Week 9 Day 2


# Elastic Load Balancers & EC2 Auto Scaling


## Elastic Load Balancers





## EC2 Auto Scaling


```PowerShell

aws elbv2 create-load-balancer \
--name MY-LOAD-BALANCER \
--subnets SUBNET \
--security-groups SG-12345667

```

```JSON
{
"LoadBalancers": [{ "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-east-1:123456789012:loadbalancer/app/my-load-balancer/1234567890123456", "DNSName": "my-load-balancer-1234567890123456.us-east-1.elb.amazonaws.com", "CanonicalHostedZoneId": "Z35SXDOTRQ7X7K", "CreatedTime": "2019-03-28T16:33:59.670Z", "LoadBalancerName": "my-load-balancer", "Scheme": "internet-facing", "VpcId": "vpc-1234567890123",
```
#
