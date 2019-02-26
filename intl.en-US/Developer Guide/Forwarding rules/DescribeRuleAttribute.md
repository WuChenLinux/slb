# DescribeRuleAttribute {#doc_api_879547 .reference}

You can call the DescribeRuleAttribute API to query the settings of a specified forwarding rule.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeRuleAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeRuleAttribute|The action to perform. Valid value: **DescribeRuleAttribute**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can call the [DescribeRegions](~~27584~~) API to query the region ID.

 |
|RuleId|String|Yes|rule-bp1efemp9suk5|The ID of the forwarding rule

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RuleName|String|Rule1|The name of the forwarding rule

 |
|LoadBalancerId|String|lb-bp1ca0zt07t934wxezyxo|The ID of the SLB instance

 |
|ListenerPort|String|90|The frontend listener port used by the SLB instance

 |
|Domain|String|test.com|The domain name of the forwarding rule

 |
|Url|String|/cache|The forwarding rule path

 |
|VServerGroupId|String|rsp-cige6j5e7p|The ID of the server group relating to the forwarding rule

 |
|Cookie|String|wwe|The cookie configured on the server.

 It can contain 1 to 200 characters, including only ASCII letters and numbers. It cannot contain commas \(,\), semicolons \(;\), or spaces or start with a dollar sign \($\).

 This parameter is required and takes effect only when **StickySession** is set to **on** and **StickySessionType** is set to **server**.

 |
|CookieTimeout|Integer|12|Timeout period of the Cookie.

 Valid values: **1–86400** \(seconds\)

 **Note:** This parameter is required and takes effect only when **StickySession** is set to **on** and **StickySessionType** is set to **insert**.

 |
|HealthCheck|String|off|Whether to enable health checks.

 Valid values: **on | off**.

 **Note:** This parameter takes effect when **ListenerSync** is set to **off**. Listener settings take precedence when this parameter is set to **on**.

 |
|HealthCheckConnectPort|Integer|23|The port of the backend server for health checks.

 Valid values: **1–65535**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**. By default, backend listener settings take precedence if this parameter is empty and **HealthCheck** is set to **on**.

 |
|HealthCheckDomain|String|www.example.com|The domain name used for health checks. Valid values:

 -   **$\_ip**: private IP address of the backend server. When the IP address is specified or this parameter is not specified, SLB uses the private IP addresses of backend servers as the domain names for health checks.
-   **domain**: domain name, which can contain 1 to 80 characters, including letters, numbers, periods \(.\), and hyphens \(-\).

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|HealthCheckHttpCode|String|http\_3xx|The HTTP status code indicating that the health check is normal. Separate multiple status codes by commas. Default value: **http\_2xx**.

 Valid values: **http\_2xx | http\_3xx | http\_4xx | http\_5xx**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|HealthCheckInterval|Integer|34|The time interval between two consecutive health checks.

 Valid values: **1–50** \(seconds\)

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|HealthCheckTimeout|Integer|34|The amount of time to wait for the response from a health check. If the backend ECS does not send a response within the specified time, the health check fails.

 Valid values: **1–300** \(seconds\)

 **Note:** If the value of this parameter**** is smaller than that of **HealthCheckInterval**, this parameter is invalid****, and the timeout is the value of **HealthCheckInterval**. This parameter takes effect when **HealthCheck** is set to **on**.

 |
|HealthCheckURI|String|10.21.22.1|The URI used for health checks.

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|HealthyThreshold|Integer|2|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|ListenerSync|String|off|Whether a forwarding rule inherits the settings of a health check, session persistence, and scheduling algorithm from a listener.

 Valid values: **on | off**

 -   **off**: The rule customs health check and session persistence settings instead of inheriting them from the listener.
-   **on**: The rule inherits the settings from the listener.

 |
|RequestId|String|9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C|The ID of the request

 |
|Scheduler|String|wrr|The algorithm used to distribute traffic. Valid values:

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A backend server with a higher weight will receive more requests.

When the weight is the same, the server with a smaller number of connections is more likely to be polled.

 -   **rr**: Requests are evenly and sequentially distributed to the backend servers.

 **Note:** This parameter takes effect when **ListenerSync** is set to **off**. Listener settings prevail when this parameter is set to **on**.

 |
|StickySession|String|off|Whether to enable session persistence.

 Valid values: **on | off**

 **Note:** This parameter is required and takes effect when **ListenerSync** is set to **off**. Listener settings take precedence when this parameter is set to **on**.

 |
|StickySessionType|String|insert|The method used to handle the Cookie. Valid values:

 -   **insert**: Insert the Cookie. When a client accesses SLB for the first time, SLB inserts Cookies into response requests \(that is, SLB inserts SERVERID into the HTTP/HTTPS response data packets\). The next time the client accesses SLB with the Cookies, SLB will direct and forward the requests to the previously recorded backend server.
-   **server**: Rewrite the Cookie. SLB will overwrite the original cookie when a new cookie is set. The next time the client carries the new cookie to access SLB, the listener will distribute the request to the previously recorded backend server.

 **Note:** This parameter takes effect when **StickySession** is set to **on**.

 |
|UnhealthyThreshold|Integer|3|Number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeRuleAttribute
&RegionId=cn-hangzhou
&RuleId=rule-bp1efemp9suk5
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeRuleAttributeResponse>
  <Domain>test.com</Domain>
  <VServerGroupId>rsp-bp114nimo4kl9</VServerGroupId>
  <LoadBalancerId>lb-bp1ca0zt07t934wxezyxo</LoadBalancerId>
  <RuleName>Rule2</RuleName>
  <ListenerPort>90</ListenerPort>
  <RequestId>DB3C28EE-9A6C-4FFA-8759-4ED8346A675E</RequestId>
  <ListenerSync>on</ListenerSync>
</DescribeRuleAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Domain":"test.com",
	"RequestId":"DB3C28EE-9A6C-4FFA-8759-4ED8346A675E",
	"VServerGroupId":"rsp-bp114nimo4kl9",
	"LoadBalancerId":"lb-bp1ca0zt07t934wxezyxo",
	"RuleName":"Rule2",
	"ListenerSync":"on",
	"ListenerPort":90
}
```

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

