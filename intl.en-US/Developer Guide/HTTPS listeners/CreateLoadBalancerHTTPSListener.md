# CreateLoadBalancerHTTPSListener {#doc_api_926265 .reference}

You can call the CreateLoadBalancerHTTPSListener API to create an HTTPS listener.

**Note:** The status of a newly created listener is stopped. After a listener is created, you must call the [StartLoadBalancerListener](~~27597~~) API to start the listener to forward traffic.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=CreateLoadBalancerHTTPSListener) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|CreateLoadBalancerHTTPSListener|The action to perform. Valid value: **CreateLoadBalancerHTTPSListener**

 |
|Bandwidth|Integer|Yes|-1|The peak bandwidth of the listener. Valid values: **-1 | 1–5000**

 -   **-1**: You can set the peak bandwidth to **-1** for an Internet instance that is billed by traffic. Then, the peak bandwidth is not limited.
-   **1–5000** \(Mbit/s\): For an Internet instance that is billed by bandwidth, you can set one peak bandwidth for each listener. However, the sum of the peak bandwidth values of all listeners cannot surpass the peak bandwidth of the instance. For more information, see [Share bandwidth](~~57846~~).

 |
|HealthCheck|String|Yes|on|Whether to enable health checks. Valid values: **on | off**.

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp1o94dp5i6earr9g6d1l|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |
|ServerCertificateId|String|Yes|idkp-123-cn-test-01|The ID of the server certificate

 |
|StickySession|String|Yes|on|Whether to enable session persistence.

 Valid values: **on | off**.

 |
|AclId|String|No|123|The ID of the access control list bound to the listener.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|AclStatus|String|No|off|Whether to enable access control.

 Valid values: **on | off** \(default value\)

 |
|AclType|String|No|white|The access control type:

 -   **white**: Indicates a whitelist. Only requests from IP addresses or CIDR blocks in the selected access control lists are forwarded. It applies to scenarios where an application only allows access from specific IP addresses.

Enabling a whitelist poses some risks to your services.

 After a whitelist is enabled, only the IP addresses in the list can access the listener.

 If you enable a whitelist without adding any IP addresses in the list, all requests are forwarded.

 -   **black**: Indicates a blacklist. Requests from IP addresses or CIDR blocks in the selected access control lists are not forwarded \(that is, they are blocked\). It applies to scenarios where an application only denies access from specific IP addresses.

If you enable a blacklist without adding any IP addresses in the list, all requests are forwarded.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|BackendServerPort|Integer|No|80|The backend port used by the SLB instance. Valid values: **1–65535**.

 If the VServerGroupId parameter is not specified, this parameter is required.

 |
|CACertificateId|String|No|139a00604ad-cn-east-hangzhou-01|The ID of the CA certificate.

 If both the CA certificate and the server certificate are uploaded, two-way authentication is established.

 If you upload only the server certificate, one-way authentication is established.

 |
|Cookie|String|No|B490B5EBF6F3CD402E515D22BCDA1598|The cookie configured on the backend server.

 The cookie must be 1 to 200 characters in length and can only contain ASCII English letters and numbers. It cannot contain commas \(,\), semicolons \(;\), or spaces, nor can it begin with $.

 This parameter is required when the value of **StickySession** is **on** and the value of **StickySessionType** is **server**.

 |
|CookieTimeout|Integer|No|500|Timeout period of the cookie.

 Valid values: **1–86400** \(seconds\)

 This parameter is required when the value of **StickySession** is **on**, and the value of **StickySessionType** is **insert**.

 |
|Description|String|No|Create a listener|A description of the listener.

 The description must be 1 to 80 characters in length and can contain letters, numbers, hyphens \(-\), slashes \(/\), periods \(.\), and underscores \(\_\). Chinese characters are supported.

 |
|EnableHttp2|String|No|off|Whether to enable the HTTP/2 feature.

 Valid values: **on** \(default value\)**| off**

 |
|Gzip|String|No|on|Whether to enable Gzip compression to compress a specific file type.

 Valid values: **on** \(default value\)**| off**

 |
|HealthCheckConnectPort|Integer|No|8080|The port used for health checks.

 Valid values: **1–65535**

 |
|HealthCheckDomain|String|No|$\_ip|The domain name used for health checks. Valid values:

 **$\_ip**: the private IP address of the backend server. When the IP address is specified or this parameter is not specified, SLB uses private IP addresses of backend servers as the domain names for health checks.

 **domain**: The domain name must be 1 to 80 characters in length, and can only contain letters, numbers, periods \(.\), and hyphens \(-\).

 |
|HealthCheckHttpCode|String|No|http\_2xx,http\_3xx|The HTTP status code indicating that the health check is normal. Separate multiple HTTP status codes by commas. Default value: **http\_2xx**.

 Valid values: **http\_2xx | http\_3xx | http\_4xx | http\_5xx**

 |
|HealthCheckInterval|Integer|No|5|The time interval between two consecutive health checks.

 Valid values: **1–50** \(seconds\)

 |
|HealthCheckTimeout|Integer|No|3|The amount of time to wait for the response from the health check. If the backend ECS instance does not send a correct response within the specified time, the health check fails.

 Valid values: **1–300** \(seconds\)

 **Note:** If the value of **HealthCheckInterval** is greater than the value of **HealthCheckTimeout** , the **HealthCheckTimeout** parameter is invalid, and the timeout is set to the value of **HealthCheckInterval**.

 |
|HealthCheckURI|String|No|/test/index.html|The URI used for health checks

 |
|HealthyThreshold|Integer|No|4|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 |
|IdleTimeout|Integer|No|12|Specify the idle connection timeout in seconds. Valid values: 1–60. Default value: 15.

 If no request is received during the specified timeout period, SLB will temporarily terminate the connection and restart the connection when the next request is received.

 |
|RequestTimeout|Integer|No|23|Specify the request timeout in seconds. Valid values: 1–180. Default value: 60.

 If no response is received from the backend server during the specified timeout period, SLB will stop waiting and send an HTTP 504 error to the client.

 |
|Scheduler|String|No|wrr|The algorithm used to distribute traffic. Valid values:

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A server with a higher weight will receive more requests. When the weight value is the same, the backend server with a smaller number of connections is more likely to be polled.
-   **rr**: Requests are evenly and sequentially distributed to the backend servers.

 |
|StickySessionType|String|No|on|on

 Valid values: **insert | server**

 -   **insert**: Insert the cookie.

SLB adds a cookie to the first response from the backend server \(that is, it inserts SERVERID in the HTTP/HTTPS response packet\). Then, the next request will contain the cookie and the listener will distribute the request to the same backend server.

 -   **server**: Rewrite the cookie.

SLB will overwrite the original cookie when a new cookie is set. The next time the client carries the new cookie to access SLB, the listener will distribute the request to the previously recorded backend server.

 |
|TLSCipherPolicy|String|No|tls\_cipher\_policy\_1\_1|You can only specify the TLSCipherPolicy parameter for guaranteed-performance instances. Each security policy includes the TLS protocol versions that can be selected by HTTPS and the supporting cipher suites.

 Currently, the following four security policies are supported. For more information about their differences, see the introduction to the differences of the TLS security policies.

 -   **tls\_cipher\_policy\_1\_0**:

Supported TLS versions: TLSv1.0, TLSv1.1, and TLSv1.2.

 Supported encryption algorithm suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA, and DES-CBC3-SHA.

 -   **tls\_cipher\_policy\_1\_1**:

Supported TLS versions: TLSv1.1 and TLSv1.2.

 Supported encryption algorithm suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384、AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA, and DES-CBC3-SHA.

 -   **tls\_cipher\_policy\_1\_2**

Supported TLS version: TLSv1.2.

 Supported cipher suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256、AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA, and DES-CBC3-SHA.

 -   **tls\_cipher\_policy\_1\_2\_strict**

Supported TLS version: TLSv1.2.

 Supported cipher suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, ECDHE-RSA-AES128-SHA, and ECDHE-RSA-AES256-SHA.

 |
|UnhealthyThreshold|Integer|No|4|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 |
|VServerGroupId|String|No|rsp-cige6j5e7p|The ID of the VServer group.

 |
|XForwardedFor|String|No|on|X-Forwarded-For

 Valid values: **on** \(default value\)**| off**

 |
|XForwardedFor\_SLBID|String|No|on|Whether to use the SLB-ID header field to obtain the ID of the SLB instance.

 Valid values: **on | off** \(default value\)

 |
|XForwardedFor\_SLBIP|String|No|on|Whether to use the SLB-IP header field to obtain the real IP address of a visitor.

 Valid values: **on | off** \(default value\)

 |
|XForwardedFor\_proto|String|No|on|Whether to use the X-Forwarded-Proto header field to obtain the listener protocol of the SLB instance.

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

http(s)://[Endpoint]/? Action=CreateLoadBalancerHTTPSListener
&Bandwidth=-1
&HealthCheck=on
&ListenerPort=80
&LoadBalancerId=lb-bp1o94dp5i6earr9g6d1l
&ServerCertificateId=idkp-123-cn-test-01
&StickySession=on
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<CreateLoadBalancerHTTPSListenerResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</CreateLoadBalancerHTTPSListenerResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
}
```

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

