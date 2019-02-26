# SetLoadBalancerHTTPListenerAttribute {#doc_api_883170 .reference}

You can call the SetLoadBalancerHTTPListenerAttribute API to modify the configurations of an HTTP listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetLoadBalancerHTTPListenerAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetLoadBalancerHTTPListenerAttribute|The action to perform. Valid value: **SetLoadBalancerHTTPListenerAttribute**

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance.

 Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp1qjwo61pqz3ahltv0mw|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |
|AclId|String|No|123|The ID of the access control list bound to the listener.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|AclStatus|String|No|off|Whether to enable access control.

 Valid values: **on | off**

 |
|AclType|String|No|white|The access control type:

 -   **white**: Indicates a whitelist. Only requests from the IP addresses or CIDR blocks in the selected access control lists are forwarded. It applies to scenarios where an application allows access only from specific IP addresses.

Enabling a white access control list poses some risks to your services.

 After a whitelist is enabled, only the IP addresses in the list can access the listener.

 If you enable a whitelist without adding any IP addresses to the list, all requests are forwarded.

 -   **black**: Indicates a blacklist. Requests from the IP addresses or CIDR blocks in the selected access control lists are not forwarded \(that is, they are blocked\). It applies to scenarios where an application denies access only from specific IP addresses.

If you enable a blacklist without adding any IP addresses to the list, all requests are forwarded.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|Bandwidth|Integer|No|-1|The peak bandwidth of the listener \(unit: Mbit/s\). Valid values: **-1 | 1–5000**

 -   **-1**: You can set the peak bandwidth of an Internet SLB instance that is billed by traffic to **-1**. Then, the peak bandwidth is not restricted.

 |
|Cookie|String|No|B490B5EBF6F3CD402E515D22BCDA1598|The cookie configured on the server.

 The cookie must be **1 to 200** characters in length and can only contain ASCII English letters and numeric characters. It cannot contain commas \(,\), semicolons \(;\), or spaces, nor can it begin with $.

 This parameter is required when the value of **StickySession** is **on** and the value of **StickySessionType** is **server**.

 |
|CookieTimeout|Integer|No|500|Timeout period of the cookie.

 Valid values: **1–86400** \(seconds\).

 This parameter is required when the value of **StickySession** is **on** and the value of **StickySessionType** is **insert**.

 |
|Description|String|No|test|A description of the listener

 |
|Gzip|String|No|on|Whether to enable Gzip compression to compress a specific file type

 |
|HealthCheck|String|No|on|Whether to enable health checks.

 Valid values: **on | off**.

 |
|HealthCheckConnectPort|Integer|No|8080|The port used for health checks.

 Valid values: **1–65535**

 |
|HealthCheckDomain|String|No|$\_ip|The domain name used for health checks. Valid values:

 -   **$\_ip**: the private IP address of the backend server. If you specify $\_ip or do not specify HealthCheckDomain, SLB uses the private IP addresses of backend servers as domain names used for health checks.
-   **domain**: The domain name must be 1 to 80 characters in length, and can only contain letters, numbers, periods \(.\), and hyphens \(-\).

 |
|HealthCheckHttpCode|String|No|http\_2xx,http\_3xx|The HTTPS status codes indicating that the health check is normal. Separate multiple HTTP status codes by commas.

 Valid values: **http\_2xx|http\_3xx |http\_4xx|http\_5xx**

 |
|HealthCheckInterval|Integer|No|5|The time interval between two consecutive health checks. Valid values: **1–50** \(seconds\)

 |
|HealthCheckTimeout|Integer|No|3|The amount of time to wait for the response from a health check. If the backend ECS instances do not send a correct response within the specified time, the health check fails.

 Valid values: **1–300** \(seconds\)

 **Note:** If the value of **HealthCheckInterval** is greater than the value of **HealthCheckTimeout** , the value of **HealthCheckTimeout** is invalid, and the timeout is set to the valued of **HealthCheckInterval**.

 |
|HealthCheckURI|String|No|/test/index.html|The URI used for health checks

 |
|HealthyThreshold|Integer|No|4|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 |
|IdleTimeout|Integer|No|12|Specify the idle connection timeout in seconds. Valid values: 1–60. Default value: 15.

 If no request is received during the specified timeout period, SLB will temporarily terminate the connection and restart the connection when the next request is received.

 |
|RequestTimeout|Integer|No|3|Specify the request timeout in seconds. Valid values: 1–180. Default value: 60.

 If no response is received from the backend server during the specified timeout period, SLB will stop waiting and send an HTTP 504 error to the client.

 |
|Scheduler|String|No|wrr|The algorithm used to distribute traffic. Valid values:

 -   **wrr**: A backend server with a higher weight is more likely to be polled.
-   **lc**: A server with a higher weight will receive more requests.

When the weight is the same, the backend server with a smaller number of connections is more likely to be polled.

 -   **rr**: Requests are evenly and sequentially distributed to backend servers.

 |
|StickySession|String|No|on|Whether to enable session persistence. Valid values: **on | off**

 |
|StickySessionType|String|No|on|The method used to handle the cookie. Valid values:

 -   **insert**: Insert the cookie.

SLB adds a cookie to the response \(that is, it inserts SERVERID in the HTTP/HTTPS response packet\) after it receives the first request from a client. The next request will contain the cookie and the listener will distribute the request to the same backend server.

 -   **server**: Rewrite the cookie.

SLB will overwrite the original cookie when it discovers that a new cookie is set. The next time the client carries the new cookie to access SLB, the listener will distribute the request to the previously recorded backend server.

 **Note:** When the value of **StickySession** is set to **on**, this parameter is required.

 |
|UnhealthyThreshold|Integer|No|4|The number of consecutive failures of health checks on the same ECS instance before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 |
|VServerGroup|String|No|on|Whether to use a VServer group.

 Valid values: **on | off**

 |
|VServerGroupId|String|No|rsp-cige6j5e7p|The ID of the VServer group

 |
|XForwardedFor|String|No|on|Whether to get the real IP address from a client request through **X-Forwarded-For**.

 Valid values: **on \(default value\) | off**

 |
|XForwardedFor\_SLBID|String|No|on|SLB-ID

 Valid values: **on | off** \(default value\).

 If you do not set this parameter, the default value is used.

 |
|XForwardedFor\_SLBIP|String|No|on|SLB-IP

 Valid values: **on | off** \(default value\).

 **Note:** If you do not set this parameter, the default value is used.

 |
|XForwardedFor\_proto|String|No|on|X-Forwarded-Proto

 Valid values: **on | off** \(default value\).

 If you do not set this parameter, the default value is used.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=SetLoadBalancerHTTPListenerAttribute
&ListenerPort=80
&LoadBalancerId=lb-bp1qjwo61pqz3ahltv0mw
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetLoadBalancerHTTPListenerAttributeResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</SetLoadBalancerHTTPListenerAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
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

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Operation.NotAllowed|Operation Denied. The HTTP listener doesn't support this action.|The operation is not allowed. An unfinished purchase order exists.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

