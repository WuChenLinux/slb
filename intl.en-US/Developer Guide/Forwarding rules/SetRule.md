# SetRule {#doc_api_879521 .reference}

You can call the SetRule API to change the destination VServer group of a forwarding rule.

## Debug {#apiExplorer .section}

Click [Here](https://api.aliyun.com/#product=Slb&api=SetRule) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetRule|The action to perform. Valid value: **SetRule**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can call the [DescribeRegions](~~27584~~) API to query the region ID.

 |
|RuleId|String|Yes|rule-3ejhktkaeu|The ID of the forwarding rule

 |
|VServerGroupId|String|Yes|rsp-cige6j5e7p|The ID of the destination server group of the forwarding rule.

 |
|Cookie|String|No|23ffsa|The cookie configured on the server.

 It must be 1 to 200 characters in length and can contain ASCII letters and numbers. It cannot contain commas \(,\), semicolons \(;\), or spaces, or start with a dollar sign \($\).

 This parameter is required and takes effect only when **StickySession** is set to **on** and **StickySessionType** is set to **server**.

 |
|CookieTimeout|Integer|No|123|Timeout period of the cookie.

 Valid values: 1–86400 \(seconds\)

 This parameter is required and takes effect only when **StickySession** is set to **on** and **StickySessionType** is set to **insert**.

 |
|HealthCheck|String|No|off|Whether to enable health checks.

 Valid values: **on | off**

 **Note:** This parameter is required and takes effect only when **ListenerSync** is set to **off**.

 |
|HealthCheckConnectPort|Integer|No|80|The port used for health checks.

 Valid values: 1–65535

 **Note:** This parameter takes effect only when **HealthCheck** is set to **on**.

 |
|HealthCheckDomain|String|No|domain|The domain name used for health checks. Valid values:

 -   **$\_ip**: private IP address of the backend server. When $\_ip is specified or HealthCheckDomain is not specified, SLB uses the private IP addresses of backend servers as the domain names for health checks.
-   **domain**: domain name, which must be 1 to 80 characters in length and can contain letters, numbers, periods \(.\). and hyphens \(-\).

 **Note:** The two parameters take effect only when **HealthCheck** is set to **on**.

 |
|HealthCheckHttpCode|String|No|http\_2xx|The HTTP status code indicating that the health check is normal. Separate multiple status codes by commas.

 This parameter is required when **HealthCheck** is set to **on**.

 Valid values: **http\_2xx** \(default value\)**| http\_3xx | http\_4xx | http\_5xx**

 **Note:** This parameter takes effect only when **HealthCheck** is set to **on**.

 |
|HealthCheckInterval|Integer|No|20|The time interval between two consecutive health checks.

 This parameter is required when **HealthCheck** is set to **on**.

 Valid values: **1–50** \(seconds\)

 **Note:** This parameter takes effect only when **HealthCheck** is set to **on**.

 |
|HealthCheckTimeout|Integer|No|20|The amount of time to wait for the response from a health check. If the backend ECS does not send a response within the specified time, the health check fails.

 **Note:** This parameter is required and takes effect only when **HealthCheck** is set to **on**.

 Valid values: **1–300** \(seconds\)

 |
|HealthCheckURI|String|No|/example|The URI used for health checks. This parameter is required and takes effect only when **HealthCheck** is set to **on**.

 |
|HealthyThreshold|Integer|No|12|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 This parameter is required and takes effect only when **HealthCheck** is set to **on**.

 Valid values: 2–10

 |
|ListenerSync|String|No|off|Whether a forwarding rule inherits the settings of a health check, session persistence, and scheduling algorithm from a listener.

 Valid values: **on | off**

 -   **off**: The rule customs health check and session persistence settings instead of inheriting them.
-   **on**: The rule inherits the settings from the listener.

 |
|RuleName|String|No|doctest|The name of the forwarding rule

 |
|Scheduler|String|No|wrr|This parameter is required and takes effect only when **ListenerSync** is set to **off**.

 The algorithm used to distribute traffic. Valid values:

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A backend server with a higher weight will receive more requests. When the weight value is the same, the server with a smaller number of connections is more likely to be polled.
-   **rr**: Requests are evenly and sequentially distributed to the backend servers.

 |
|StickySession|String|No|off|This parameter is required and takes effect only when **ListenerSync** is set to **off**.

 Whether to enable session persistence. Valid values: **on | off**.

 |
|StickySessionType|String|No|insert|The method used to handle the Cookie. This parameter is required and takes effect only when **StickySession** is set to **on**.

 Valid values:

 -   insert: Insert the Cookie.

When a client accesses SLB for the first time, SLB inserts Cookies into response requests \(that is, SLB inserts SERVERID into the HTTP/HTTPS response data packets\). The next time the client accesses SLB with the Cookies, SLB will direct and forward the requests to the previously recorded backend server.

 -   server: Rewrite the Cookie.

SLB will overwrite the original cookie when a new cookie is set. The next time the client carries the new cookie to access the SLB instance, the listener will distribute the request to the previously recorded backend server.

 |
|UnhealthyThreshold|Integer|No|1|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 This parameter is required and takes effect only when **HealthCheck** is set to **on**.

 Valid values: 2–10

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=SetRule
&RegionId=cn-hangzhou
&RuleId=rule-3ejhktkaeu
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetRuleResponse>
  <RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
</SetRuleResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C"
}
```

## Error codes { .section}

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidParameter|The specified VServerGroupId doesn't belong to the rule's LoadBalancerId.|The parameter Bandwidth is invalid. Please check that the parameter is correct.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

