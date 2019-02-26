# SetLoadBalancerHTTPSListenerAttribute {#doc_api_883737 .reference}

You can call the SetLoadBalancerHTTPSListenerAttribute API to modify the configurations of an HTTPS listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetLoadBalancerHTTPSListenerAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetLoadBalancerHTTPSListenerAttribute|The action to perform. Valid value: **SetLoadBalancerHTTPSListenerAttribute**

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance.

 Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|139a00604ad-cn-east-hangzhou-01|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |
|AclId|String|No|56565|The ID of the access control list bound to the listener.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|AclStatus|String|No|off|Whether to enable access control.

 Valid values: **on | off**

 |
|AclType|String|No|white|The access control type:

 -   **white**: Indicates a whitelist. Only requests from IP addresses or CIDR blocks in the selected access control lists are forwarded. It applies to scenarios where an application only allows access from specific IP addresses.

Enabling a whitelist poses some risks to your services. After a whitelist is enabled, only the IP addresses in the list can access the listener. If you enable a whitelist without adding any IP addresses in the list, all requests are forwarded.

 -   **black**: Indicates a blacklist. Requests from IP addresses or CIDR blocks in the selected access control lists are not forwarded \(that is, they are blocked\). It applies to scenarios where an application only denies access from specific IP addresses.

If you enable a blacklist without adding any IP addresses in the list, all requests are forwarded.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|Bandwidth|Integer|No|-1|The peak bandwidth of the listener. Valid values:

 -   **-1**: The peak bandwidth is not limited.
-   **1–5000**: The peak bandwidth of the listener. The sum of the peak bandwidth values of all listeners cannot surpass the peak bandwidth of the instance.

 |
|CACertificateId|String|No|139a00604ad-cn-east-hangzhou-01|The ID of the CA certificate.

 If both the CA certificate and the server certificate are uploaded, mutual authentication is established. If only the server certificate is uploaded, one-way authentication is established.

 |
|Cookie|String|No|B490B5EBF6F3CD402E515D22BCDA1598|The cookie configured on the backend server.

 The cookie must be 1-200 characters in length and can only contain ASCII English letters and numbers. It cannot contain commas \(,\), semicolons \(;\), or spaces, nor can it begin with $.

 This parameter is required when the value of **StickySession** is **on** and the value of **StickySessionType** is **server**.

 |
|CookieTimeout|Integer|No|500|Timeout period of the cookie.

 Valid values: **1–86400** \(seconds\).

 **Note:** This parameter is required when the value of **StickySession** is **on**, and the value of **StickySessionType** is **insert**.

 |
|Description|String|No|A description of the listener|A description of the listener

 |
|EnableHttp2|String|No|off|Whether to enable the HTTP/2 feature.

 Valid values: **on | off**

 |
|Gzip|String|No|on|Whether to enable Gzip compression to compress a specific file type

 Valid values: **on | off** \(default value\).

 |
|HealthCheck|String|No|on|Whether to enable health checks.

 Valid values: **on | off**

 |
|HealthCheckConnectPort|Integer|No|8080|The port used for health checks.

 Valid values: **1–65535**

 |
|HealthCheckDomain|String|No|$\_ip|The domain name used for health checks. Valid values:

 -   **$\_ip**: the private IP address of the backend server. When the IP address is specified or this parameter is not specified, SLB uses private IP addresses of backend servers as the domain names for health checks.
-   **domain**: The domain name must be 1 to 80 characters in length, and can only contain letters, numbers, periods \(.\), and hyphens \(-\).

 |
|HealthCheckHttpCode|String|No|http\_2xx,http\_3xx|The HTTP status code indicating that the health check is normal. Separate multiple HTTP status codes by commas.

 Valid values: **http\_2xx | http\_3xx | http\_4xx | http\_5xx**

 |
|HealthCheckInterval|Integer|No|5|The time interval between two consecutive health checks.

 Valid values: **1–50** \(seconds\)

 |
|HealthCheckTimeout|Integer|No|3|The amount of time to wait for the response from the health check. If the backend ECS instance does not send a correct response within the specified time, the health check fails.

 Valid values: **1–300** \(seconds\).

 **Note:** If the value of **HealthCheckInterval** is greater than the value of **HealthCheckTimeout**, the **HealthCheckTimeout** parameter is invalid, and the timeout is set to the value of **HealthCheckInterval**.

 |
|HealthCheckURI|String|No|/test/index.html|The URI used for health checks

 |
|HealthyThreshold|Integer|No|4|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 |
|IdleTimeout|Integer|No|23|Specify the idle connection timeout in seconds. Valid values: 1–60. Default value: 15.

 If no request is received during the specified timeout period, SLB will temporarily terminate the connection and restart the connection when the next request is received.

 |
|RequestTimeout|Integer|No|223|Specify the request timeout in seconds. Valid values: 1–180. Default value: 60.

 If no response is received from the backend server during the specified timeout period, SLB will stop waiting and send an HTTP 504 error to the client.

 |
|Scheduler|String|No|wrr|The algorithm used to distribute traffic. Valid values:

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A server with a higher weight will receive more requests. When the weight value is the same, the backend server with a smaller number of connections is more likely to be polled.
-   **rr**: Requests are evenly and sequentially distributed to the backend servers.

 |
|ServerCertificateId|String|No|idkp-123-cn-test-01|The ID of the server certificate

 |
|StickySession|String|No|on|Whether to enable session persistence. Valid values: **on | off**.

 |
|StickySessionType|String|No|on|The method used to handle the cookie. Valid values:

 -   **insert**: Insert the cookie.

SLB adds a cookie to the first response from the backend server \(that is, it inserts SERVERID in the HTTP/HTTPS response packet\). Then, the next request will contain the cookie and the listener will distribute the request to the same backend server.

 -   **server**: Rewrite the cookie.

SLB will overwrite the original cookie when a new cookie is set. The next time the client carries the new cookie to access SLB, the listener will distribute the request to the previously recorded backend server.

 **Note:** When the value of **StickySession** is **on**, this parameter is required.

 |
|TLSCipherPolicy|String|No|tls\_cipher\_policy\_1\_2|You can only specify the TLSCipherPolicy parameter for guaranteed-performance instances. Each security policy includes the TLS protocol versions that can be selected by HTTPS and the supporting cipher suites.

 Currently, the following four security policies are supported:

 -   **tls\_cipher\_policy\_1\_0**:
-   Supported TLS versions: TLSv1.0, TLSv1.1, and TLSv1.2.
-   Supported encryption algorithm suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA, and DES-CBC3-SHA.
-   **tls\_cipher\_policy\_1\_1**:
-   Supported TLS versions: TLSv1.1 and TLSv1.2.
-   Supported encryption algorithm suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA, and DES-CBC3-SHA.
-   **tls\_cipher\_policy\_1\_2**
-   Supported TLS version: TLSv1.2.
-   Supported cipher suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA, and DES-CBC3-SHA.
-   **tls\_cipher\_policy\_1\_2\_strict**
-   Supported TLS version: TLSv1.2.
-   Supported cipher suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, ECDHE-RSA-AES128-SHA, and ECDHE-RSA-AES256-SHA.

 |
|UnhealthyThreshold|Integer|No|4|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 |
|VServerGroup|String|No|on|Whether to use a VServer group. Valid values: **on | off**

 |
|VServerGroupId|String|No|rsp-cige6j5e7p|The ID of the VServer group.

 |
|XForwardedFor|String|No|on|Whether to use the X-Forwarded-For header field to obtain the real IP address of a client.

 Valid values: **on | off**

 |
|XForwardedFor\_SLBID|String|No|on|SLB-ID

 Valid values: **on | off** \(default value\)

 |
|XForwardedFor\_SLBIP|String|No|on|SLB-IP

 Valid values: **on | off** \(default value\)

 |
|XForwardedFor\_proto|String|No|on|X-Forwarded-Proto

 Valid values: **on | off** \(default value\)

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=SetLoadBalancerHTTPSListenerAttribute
&ListenerPort=80
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetLoadBalancerHTTPSListenerAttributeResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</SetLoadBalancerHTTPSListenerAttributeResponse>

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

[Click here to view the error codes.<span data-goldlog="/cat.main.addNote" class="next-icon next-icon-AddNote next-icon-medium add-note-icon"\>](https://error-center.aliyun.com/status/product/Slb)

