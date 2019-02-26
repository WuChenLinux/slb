# CreateLoadBalancerTCPListener {#doc_api_926143 .reference}

You can call the CreateLoadBalancerTCPListener API to create a TCP listener.

**Note:** The status of a newly created listener is stopped. After a listener is created, you must call the [StartLoadBalancerListener](~~27597~~) API to start the listener to forward traffic.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=CreateLoadBalancerTCPListener) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|CreateLoadBalancerTCPListener|The action to perform. Valid value: **Createloadbalancertcplistener**

 |
|Bandwidth|Integer|Yes|-1|The peak bandwidth of the listener. Valid values: **-1 | 1–5000**.

 -   **-1**: You can set the peak bandwidth to **-1** for an Internet instance that is billed by traffic. Then, the peak bandwidth is not limited.
-   **1–5000** \(Mbit/s\): For an Internet instances that is billed by bandwidth, you can set one peak bandwidth for each listener. However, the sum of the peak bandwidth values of all listeners cannot surpass the peak bandwidth of the instance. For more information, see [Share bandwidth](~~57846~~).

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp1b6c719dfa08exfuca5|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |
|AclId|String|No|1323|The ID of the access control list bound to the listener.

 If the value of **AclStatus** is **on**, this parameter is required.

 |
|AclStatus|String|No|off|Whether to enable access control.

 Valid values: **on | off** \(default value\)

 |
|AclType|String|No|black|The access control type:

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
|Description|String|No|Create a listener.|A description of the listener.

 The description must be 1 to 80 characters in length and can contain letters, numbers, hyphens \(-\), slashes \(/\), periods \(.\), and underscores \(\_\). Chinese characters are supported.

 |
|EstablishedTimeout|Integer|No|500|The connection timeout value. Valid values: **10–900** \(seconds\)

 |
|HealthCheckConnectPort|Integer|No|80|The port used for health checks. Valid values: **1–65535**

 If you do not set this parameter, the backend service port \(BackendServerPort\) is used.

 |
|HealthCheckConnectTimeout|Integer|No|100|The maximum timeout value for each health check response. Valid values: **1–300** \(seconds\)

 Default value: 5

 |
|HealthCheckDomain|String|No|$\_ip|The domain name used for health checks. Valid values:

 -   **$\_ip**: the private IP address of the backend server. When the IP address is specified or this parameter is not specified, SLB uses private IP addresses of backend servers as the domain names for health checks.
-   **domain**: The domain name must be 1 to 80 characters in length, and can only contain letters, numbers, periods \(.\), and hyphens \(-\).

 |
|HealthCheckHttpCode|String|No|http\_2xx,http\_3xx|The HTTP status code indicating that the health check is normal. Separate multiple HTTP status codes by commas.

 Valid values: **http\_2xx \(default value\) | http\_3xx | http\_4xx | http\_5xx**

 |
|HealthCheckType|String|No|tcp|The health check type. Valid values: **tcp \(default value\) | http**

 |
|HealthCheckURI|String|No|/test/index.html|The URI used for health checks.

 You can set this parameter when the TCP listener requires HTTP health checks. If you do not set this parameter, TCP health checks are performed.

 |
|HealthyThreshold|Integer|No|4|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 |
|MasterSlaveServerGroupId|String|No|rsp-0bfucwuotx|The ID of the active/standby server group.

 **Note:** You can only choose either VServerGroupId or MasterSlaveServerGroupId.

 |
|PersistenceTimeout|Integer|No|0|The timeout value of the session persistence. Valid values: **0–3600** \(seconds\)

 Default value: **0**, which indicates that session persistence is disabled.

 |
|Scheduler|String|No|wrr|The algorithm used to distribute traffic. Valid values: **wrr | wlc | rr**

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A server with a higher weight will receive more requests.

When the weight value is the same, the backend server with a smaller number of connections is more likely to be polled.

 -   **rr**: Requests are evenly and sequentially distributed to the backend servers.

 |
|UnhealthyThreshold|Integer|No|4|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: 2–10

 |
|VServerGroupId|String|No|rsp-cige6j5e7p|The ID of the VServer group

 |
|healthCheckInterval|Integer|No|3|The time interval between two consecutive health checks. Valid values: **1–50** \(seconds\)

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateLoadBalancerTCPListener
&Bandwidth=-1
&ListenerPort=80
&LoadBalancerId=lb-bp1b6c719dfa08exfuca5
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<CreateLoadBalancerTCPListenerResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</CreateLoadBalancerTCPListenerResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
}
```

## Error codes { .section}

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Abs.VServerGroupIdAndMasterSlaveServerGroupId.MissMatch|The parameters VServerGroupId or MasterSlaveServerGroupId miss match.|The parameter VServerGroupId or MasterSlaveServerGroupId does not match.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

