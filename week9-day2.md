Exit Ticket Week 9 Day 2


# Elastic Load Balancers & EC2 Auto Scaling


## Elastic Load Balancers

1. Application Load Balancer
2. Network Load Balancer
3. Classic Load Balancer

### Application Load balancer state
A load balancer can be in one of the following states:

provisioning
The load balancer is being set up.

active
The load balancer is fully set up and ready to route traffic.

active_impaired
The load balancer is routing traffic but does not have the resources it needs to scale.

failed
The load balancer could not be set up.

### Network Load balancer state
A load balancer can be in one of the following states:

provisioning
The load balancer is being set up.

active
The load balancer is fully set up and ready to route traffic.

failed
The load balancer could not be set up.

________________________________

## Rule action types

The following are the supported action types for a listener rule:

authenticate-cognito
[HTTPS listeners] Use Amazon Cognito to authenticate users. For more information, see Authenticate users using an Application Load Balancer.

authenticate-oidc
[HTTPS listeners] Use an identity provider that is compliant with OpenID Connect (OIDC) to authenticate users.

fixed-response
Return a custom HTTP response. For more information, see Fixed-response actions.

forward
Forward requests to the specified target groups. For more information, see Forward actions.

redirect
Redirect requests from one URL to another. For more information, see Redirect actions.

________________________________


## Redirect actions
You can use redirect actions to redirect client requests from one URL to another. You can configure redirects as either temporary (HTTP 302) or permanent (HTTP 301) based on your needs.

A URI consists of the following components:

```PowerShell
protocol://hostname:port/path?query
```

You must modify at least one of the following components to avoid a redirect loop: protocol, hostname, port, or path. Any components that you do not modify retain their original values.

protocol
The protocol (HTTP or HTTPS). You can redirect HTTP to HTTP, HTTP to HTTPS, and HTTPS to HTTPS. You cannot redirect HTTPS to HTTP.

hostname
The hostname. A hostname is not case-sensitive, can be up to 128 characters in length, and consists of alpha-numeric characters, wildcards (* and ?), and hyphens (-).

port
The port (1 to 65535).

path
The absolute path, starting with the leading "/". A path is case-sensitive, can be up to 128 characters in length, and consists of alpha-numeric characters, wildcards (* and ?), & (using &amp;), and the following special characters: _-.$/~"'@:+.

query
The query parameters. The maximum length is 128 characters.

#{protocol} - Retains the protocol. Use in the protocol and query components.

#{host} - Retains the domain. Use in the hostname, path, and query components.

#{port} - Retains the port. Use in the port, path, and query components.

#{path} - Retains the path. Use in the path and query components.

#{query} - Retains the query parameters. Use in the query component.

________________________________


##Rule condition types

The following are the supported condition types for a rule:

host-header
Route based on the host name of each request. For more information, see Host conditions.

http-header
Route based on the HTTP headers for each request. For more information, see HTTP header conditions.

http-request-method
Route based on the HTTP request method of each request. For more information, see HTTP request method conditions.

path-pattern
Route based on path patterns in the request URLs. For more information, see Path conditions.

query-string
Route based on key/value pairs or values in the query strings. For more information, see Query string conditions.

source-ip
Route based on the source IP address of each request. For more information, see Source IP address conditions.

________________________________

## EC2 Auto Scaling

### CLI Commands

```PowerShell
create-load-balancer
create-target-group
register-targets
create-listener
describe-target-health
```


```PowerShell
create-load-balancer

aws elbv2 create-load-balancer \
  --name MY-LOAD-BALANCER \
  --subnets SUBNET \
  --security-groups SG-12345667
  
________________________________

create-target-group

aws albv2 create-target-group \
  --name MY-TARGETS \
  --protocol HTTP \
  --port 80 \
  --vpc-id VPC-ID_NUMBER

________________________________

register-targets

aws elbv2 register-targets \
target-group-arm TARGETGROUP-ARM \
  --targets Id=ID1234567 Id=ID1234567 
________________________________

create-listener

aws elbv2 create-listener \
  --load-balancer-arm LOADBALANCER-ARM
  --protocol HTTP \
  --port 80 \
  --default-actions
Type=forward, TargetGroupArn=TARGETGROUP-ARM
________________________________

describe-target-health

aws elbv2 describe-target-health \
  --target-group-arn TARGETGROUP-ARM


________________________________

```


