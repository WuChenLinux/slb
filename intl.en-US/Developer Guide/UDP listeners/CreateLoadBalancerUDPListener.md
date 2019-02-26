# CreateLoadBalancerUDPListener {#doc_api_926171 .reference}

You can call the CreateLoadBalancerUDPListener API to create a UDP listener.

The function of obtaining real IP addresses is not supported by classic network SLB instances with the UDP protocol.

**Note:** The status of a newly created listener is **stopped**. After a listener is created, you must call the StartLoadBalancerListener API to start the listener to forward traffic.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=CreateLoadBalancerUDPListener) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|CreateLoadBalancerUDPListener|The action to perform. Valid value: **CreateLoadBalancerUDPListener**

 |
|Bandwidth|Integer|Yes|34|The peak bandwidth of the listener. Valid values: **-1 | 1–5000**

 -   **-1**: You can set the peak bandwidth to **-1** for an Internet instance that is billed by traffic. Then, the peak bandwidth is not limited.

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp1ygod3yctvg1y7wezms|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region

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
|BackendServerPort|Integer|No|80|The backend port used by the SLB instance. Valid values: **1–65535**. If the VServerGroupId parameter is not specified, this parameter is required.

 |
|Description|String|No|test|A description of the listener.

 The description must be 1 to 80 characters in length and can contain letters, numbers, hyphens \(-\), slashes \(/\), periods \(.\), and underscores \(\_\). Chinese characters are supported.

 |
|HealthCheckConnectPort|Integer|No|80|The port used for health checks. Valid values: **1–65535**

 If you do not set this parameter, the backend service port \(**BackendServerPort**\) is used.

 |
|HealthCheckConnectTimeout|Integer|No|100|The amount of time to wait for the response from the health check.

 If the backend ECS instance does not send a correct response within the specified time, the health check fails.

 Valid values: **1–300** \(seconds\)

 |
|HealthyThreshold|Integer|No|4|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 |
|MasterSlaveServerGroupId|String|No|rsp-0bfucwuotx|The ID of the active/standby server group.

 **Note:** You can only choose either VServerGroupId or MasterSlaveServerGroupId.

 |
|Scheduler|String|No|wrr|The algorithm used to distribute traffic. Valid values:

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A server with a higher weight will receive more requests. When the weight value is the same, the backend server with a smaller number of connections is more likely to be polled.
-   **rr**: Requests are evenly and sequentially distributed to the backend servers.
-   **sch**: A consistent hash based on the source IP address. Requests with the same source IP addresses are scheduled to the same backend server.
-   **tch**: A consistent hash based on the following four parameters: source IP + destination IP + source port + destination port. The same streams are scheduled to the same backend server.
-   **qch**: A consistent hash based on the QUIC Connection ID. The same QUIC Connection IDs are scheduled to the same backend servers.

 **Note:** Only guaranteed-performance instances support sch, tch, and qch.

 Currently, the Consistency Hash \(CH\) algorithm is supported in the following regions:

 -   Japan \(Tokyo\)
-   Australia \(Sydney\)
-   Malaysia \(Kuala Lumpur\)
-   Indonesia \(Jakarta\)
-   Germany \(Frankfurt\)
-   US \(Silicon Valley\)
-   US \(Virginia\)
-   UAE \(Dubai\)
-   China \(Hohhot\)

 |
|UnhealthyThreshold|Integer|No|4|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 |
|VServerGroupId|String|No|rsp-cige6j5e7p|The ID of the VServer group

 |
|healthCheckExp|String|No|12|The port used for health checks. Valid values: **1–65535**

 If you do not set this parameter, the backend service port \(**BackendServerPort**\) is used.

 |
|HealthCheckInterval|Integer|No|3|The time interval between two consecutive health checks.

 Valid values: **1–50** \(seconds\)

 |
|healthCheckReq|String|No|hello|The request string for UDP listener health checks. It must be 1 to 500 characters in length and can only contain letters and numbers.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateLoadBalancerUDPListener
&Bandwidth=34
&ListenerPort=80
&LoadBalancerId=lb-bp1ygod3yctvg1y7wezms
& <CommonParameter>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<CreateLoadBalancerUDPListenerResponse>
  <RequestId>06F00FBB-3D9E-4CCE-9D43-1A6946A75456</RequestId>
</CreateLoadBalancerUDPListenerResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"06F00FBB-3D9E-4CCE-9D43-1A6946A75456"
}
```

## Error codes { .section}

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|Abs.VServerGroupIdAndMasterSlaveServerGroupId.MissMatch|The parameters VServerGroupId or MasterSlaveServerGroupId miss match.|The parameter VServerGroupId or MasterSlaveServerGroupId does not match.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

