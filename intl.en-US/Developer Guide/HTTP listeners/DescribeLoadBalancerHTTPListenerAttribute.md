# DescribeLoadBalancerHTTPListenerAttribute {#doc_api_874444 .reference}

You can call the DescribeLoadBalancerHTTPListenerAttribute API to query the configurations of an HTTP listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeLoadBalancerHTTPListenerAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeLoadBalancerHTTPListenerAttribute|The action to perform. Valid value: **DescribeLoadBalancerHTTPListenerAttribute**

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: **1–65535**.

 |
|LoadBalancerId|String|Yes|lb-bp1o94dp5i6earr9g6d1l-cn-east-hangzhou-01|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |
|OwnerAccount|String|No|testuser@aliyun.com|Your account

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|ListenerPort|Integer|80|The frontend port used by the SLB instance

 |
|Bandwidth|Integer|-1|The peak bandwidth of the listener

 |
|Status|String|stopped|The status of the listener.

 Valid values: **starting | running | configuring | stopping | stopped**

 |
|XForwardedFor|String|on|Whether to use X-Forwarded-For to obtain a visitor's real IP address.

 Valid values: **on | off**

 |
|Scheduler|String|wrr|The algorithm used to distribute traffic.

 Valid values: **wrr | wlc | rr**

 |
|StickySession|String|on|Whether to enable session persistence.

 Valid values: **on | off** \(default value\)

 |
|StickySessionType|String|on|The method used to handle the cookie.

 If the value of **StickySession** is **on**, this parameter is required.

 Valid values: **insert | server**

 |
|CookieTimeout|Integer|500|Timeout period of the cookie

 |
|Cookie|String|B490B5EBF6F3CD402E515D22BCDA1598|The cookie configured on the backend server

 |
|HealthCheck|String|on|Whether to enable health checks.

 Valid values: **on | off**

 |
|HealthCheckDomain|String|$\_ip|The domain name used for health checks

 |
|HealthCheckURI|String|/test/index.html|The URI used for health checks

 |
|HealthyThreshold|Integer|4|The number of consecutive successes of health checks before a backend server is declared as unhealthy

 |
|UnhealthyThreshold|Integer|4|The number of consecutive failures of health checks before a backend server is declared as unhealthy

 |
|HealthCheckTimeout|Integer|3|The maximum amount of time in seconds to wait for the response from a health check

 |
|HealthCheckInterval|Integer|5|The time interval in seconds between two consecutive health checks

 |
|HealthCheckHttpCode|String|http\_2xx,http\_3xx|The HTTP status code indicating that the health check is normal

 |
|HealthCheckConnectPort|Integer|8080|The port used for health checks

 |
|VServerGroupId|String|rsp-cige6j5e7p|The ID of the VServer group

 |
|Gzip|String|on|Whether to enable Gzip compression.

 Valid values: **on | off**

 |
|AclId|String|on|The ID of the access control list bound to the listener.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|AclStatus|String|off|Whether to enable access control.

 Valid values: **on | off** \(default value\)

 |
|AclType|String|white|The access control type:

 -   **white**: Indicates a whitelist. Only requests from the IP addresses or CIDR blocks in the selected access control lists are forwarded. It applies to scenarios where an application only allows access from specific IP addresses.

Enabling a whitelist poses some risks to your services. After a whitelist is enabled, only the IP addresses in the list can access the listener. If you enable a whitelist without adding any IP addresses in the list, all requests are forwarded.

 -   **black**: Indicates a blacklist. Requests from the IP addresses or CIDR blocks in the selected access control lists are not forwarded \(that is, they are blocked\). It applies to scenarios where an application only denies access from specific IP addresses.

If you enable a blacklist without adding any IP addresses in the list, all requests are forwarded.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|BackendServerPort|Integer|80|The backend port used by the SLB instance

 |
|Description|String|test|HTTP listener description

 |
|ForwardPort|Integer|80|The port used for redirecting from HTTP to HTTPS.

 **Note:** If the value of **ListenerForward** is **off**, this parameter is not displayed.

 |
|IdleTimeout|Integer|2|Specify the idle connection timeout in seconds. Valid values: 1–60. Default value: 15.

 If no request is received during the specified timeout period, SLB will temporarily terminate the connection and restart the connection when the next request is received.

 |
|ListenerForward|String|on|Whether to enable redirecting from HTTP to HTTPS.

 -   **on**: Enable
-   **off**: Do not enable

 |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request

 |
|RequestTimeout|Integer|34|Specify the request timeout in seconds. Valid values: 1–180. Default value: 60.

 If no response is received from the backend server during the specified timeout period, SLB will stop waiting and send an HTTP 504 error to the client.

 |
|Rules| | |A description of the forwarding rule

 |
|└Domain|String|www.example.com|The domain name

 |
|└RuleId|String|1234|The ID of the forwarding rule

 |
|└RuleName|String|test|The name of the forwarding rule

 |
|└Url|String|/example|The access path

 |
|└VServerGroupId|String|123|The ID of the target VServer group of the forwarding rule

 |
|SecurityStatus|String|on|The security status

 |
|XForwardedFor\_SLBID|String|on|SLB-ID

 |
|XForwardedFor\_SLBIP|String|on|Whether to use the SLB-IP header field to obtain the real IP address of a client request

 |
|XForwardedFor\_proto|String|on|Whether to use the X-Forwarded-Proto header field to obtain the listening protocol used by the SLB instance

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeLoadBalancerHTTPListenerAttribute
&ListenerPort=80
&LoadBalancerId=lb-bp1o94dp5i6earr9g6d1l-cn-east-hangzhou-01
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeLoadBalancerHTTPListenerAttributeResponse>
  <ForwardPort>443</ForwardPort>
  <ListenerPort>80</ListenerPort>
  <Status>stopped</Status>
  <RequestId>99439CEF-192C-4B01-A45A-2D5BD5BCDA62</RequestId>
  <ListenerForward>on</ListenerForward>
</DescribeLoadBalancerHTTPListenerAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Status":"stopped",
	"RequestId":"99439CEF-192C-4B01-A45A-2D5BD5BCDA62",
	"ForwardPort":443,
	"ListenerForward":"on",
	"ListenerPort":80
}
```

Error response example

`JSON` format

``` {#json_return_failed_demo}
{
	"Message":"The specified parameter is not valid.",
	"RequestId":"0669D684-69D8-408E-A4FA-B9011E0F4E66",
	"HostId":"slb-pop.aliyuncs.com",
	"Code":"InvalidParameter"
}
```

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

