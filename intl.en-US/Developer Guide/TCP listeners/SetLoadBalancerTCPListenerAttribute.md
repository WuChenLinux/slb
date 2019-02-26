# SetLoadBalancerTCPListenerAttribute {#doc_api_880426 .reference}

You can call the SetLoadBalancerTCPListenerAttribute API to modify the configurations of a TCP listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetLoadBalancerTCPListenerAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetLoadBalancerTCPListenerAttribute|The action to perform. Valid value: **SetLoadBalancerTCPListenerAttribute**

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp1ygod3yctvg1y7wezms|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |
|AclId|String|No|12333|The ID of the access control list bound to the listener.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|AclStatus|String|No|off|Whether to enable access control.

 Valid values: **on | off**.

 |
|AclType|String|No|white|The access control type.

 -   **white**: Indicates a whitelist. Only requests from IP addresses or CIDR blocks in the selected access control lists are forwarded. It applies to scenarios where an application only allows access from specific IP addresses.

Enabling a whitelist poses some risks to your services.

 After a whitelist is enabled, only the IP addresses in the list can access the listener.

 If you enable the whitelist without adding any IP addresses in the list, all requests are forwarded.

 -   **black**: Indicates a blacklist. Requests from IP addresses or CIDR blocks in the selected access control lists are not forwarded \(that is, they are blocked\). It applies to scenarios where an application only denies access from specific IP addresses.

If you enable a blacklist without adding any IP addresses in the list, all requests are forwarded.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|Bandwidth|Integer|No|43|The peak bandwidth of the listener \(unit: of Mbit/s\). Valid values: **-1 | 1–5000**

 -   **-1**: You can set the peak bandwidth of an Internet SLB instance that is billed by traffic to **-1**. Then, the peak bandwidth is not restricted.
-   **1–5000**: You can set one peak bandwidth for each listener of an Internet SLB instance that is billed by bandwidth. However, the sum of the peak bandwidth values of all listeners cannot exceed the peak bandwidth of the instance. For more information, see [Share bandwidth](~~57846~~).

 |
|Description|String|No|test|A description of the TCP listener

 |
|EstablishedTimeout|Integer|No|500|The timeout value of the TCP connection.

 Valid values: **10–900**\(seconds\)

 |
|HealthCheckConnectPort|Integer|No|8080|The port used for health checks. Valid values: 1–65535

 If you do not set this parameter, the backend service port \(**BackendServerPort**\) is used.

 |
|HealthCheckConnectTimeout|Integer|No|100|The amount of time to wait for the response from a health check.

 If the backend ECS instance does not send a correct response within the specified time, the health check fails.

 Valid values: **1–300** \(seconds\).

 **Note:** If the value of **HealthCheckInterval** is greater than the value of **HealthCheckConnectTimeout**, the **HealthCheckConnectTimeout** parameter is invalid, and the timeout is set to the value of **HealthCheckInterval**.

 |
|HealthCheckDomain|String|No|$\_ip|The domain name used for health checks. You can set this parameter when the TCP listener requires HTTP health checks. If you do not set this parameter, TCP health checks are performed.

 -   **$\_ip**: the private IP address of the backend server.

When the IP address is specified or this parameter is not specified, SLB uses private IP addresses of backend servers as the domain names for health checks.

 -   **domain**: The domain name must be 1 to 80 characters in length, and can only contain letters, numbers, periods \(.\), and hyphens \(-\).

 |
|HealthCheckHttpCode|String|No|http\_2xx,http\_3xx|The HTTP status code indicating that the health check is normal. Separate multiple HTTP status codes by commas.

 Valid values: **http\_2xx | http\_3xx | http\_4xx | http\_5xx**

 |
|HealthCheckInterval|Integer|No|5|The time interval between two consecutive health checks. Valid values: **1–50** \(seconds\)

 |
|HealthCheckType|String|No|tcp|The health check type.

 Valid values: **tcp | http**

 |
|HealthCheckURI|String|No|/test/index.html|The URI used for health checks.

 You can set this parameter when the TCP listener requires HTTP health checks.

 If you do not set this parameter, TCP health checks are performed.

 |
|HealthyThreshold|Integer|No|4|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 |
|MasterSlaveServerGroup|String|No|on|Whether to use an active/standby server group. Valid values: **on | off**.

 The value of **VServerGroup** and the value of **MasterSlaveServerGroup** cannot be **on** at the same time.

 |
|MasterSlaveServerGroupId|String|No|rsp-cige6j5e7p|The ID of the active/standby server group.

 **Note:** You can only choose either VServerGroupId or MasterSlaveServerGroupId.

 |
|PersistenceTimeout|Integer|No|0|The timeout value of the session persistence. Valid values: **0–3600** \(seconds\)

 Default value: **0**, which indicates that session persistence is disabled.

 |
|Scheduler|String|No|wrr|The algorithm used to distribute traffic. Value values:

 -   **wrr**: A backend server with a higher weight is more likely to be polled.
-   **wlc**: A server with a higher weight will receive more requests. When the weight is the same, the backend server with a smaller number of connections is more likely to be polled.
-   **rr**: Requests are evenly and sequentially distributed to the backend servers.
-   **sch**: A consistent hash based on source IP addresses. Requests with the same source IP addresses are scheduled to the same backend server.
-   **tch**: A consistent hash based on the following four variables: source IP + destination IP + source port + destination port. The same streams are scheduled to the same backend server.

 **Note:** Only guaranteed-performance instances support sch and tch.

 |
|SynProxy|String|No|enable|Whether to enable SynProxy. SynProxy protects SLB from attacks.

 We recommend that you retain the value set by SLB in this parameter.

 Valid values:**enable | disable**

 |
|UnhealthyThreshold|Integer|No|4|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 |
|VServerGroup|String|No|on|Whether to use a VServer group. Valid values: **on | off**

 The value of **VServerGroup** and the value of **MasterSlaveServerGroup** cannot be **on** at the same time.

 |
|VServerGroupId|String|No|rsp-cige6j5e7p|The ID of the VServer group

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=SetLoadBalancerTCPListenerAttribute
&ListenerPort=80
&LoadBalancerId=lb-bp1ygod3yctvg1y7wezms
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetLoadBalancerTCPListenerAttributeResponse>
  <RequestId>59B41B53-BC4B-481A-9D8D-2A0D20B3FCD1</RequestId>
</SetLoadBalancerTCPListenerAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"59B41B53-BC4B-481A-9D8D-2A0D20B3FCD1"
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

