# DescribeRules {#doc_api_879792 .reference}

You can call the DescribeRules API to query the forwarding rules that have been configured for a specified listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeRules) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeRules|The action to perform. Valid value: **DescribeRules**.

 |
|ListenerPort|Integer|Yes|90|The frontend listener port used by the SLB instance. Valid values: 1–65535

 |
|LoadBalancerId|String|Yes|lb-bp1ca0zt07t934wxezyxo|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C|Request ID

 |
|Rules| | |A list of the forwarding rules

 |
|└RuleId|String|rule-tybqi6qkp8|The ID of a forwarding rule

 |
|└RuleName|String|Rule2|The name of the forwarding rule. The name must be 1 to 80 characters in length and can contain letters, numbers, hyphens \(-\), forward slashes \(/\), periods \(.\), and underscores \(\_\).

 **Note:** In a listener, the name of each rule must be unique.

 |
|└Domain|String|test.com|The request domain name attached to a forwarding rule

 |
|└Url|String|/cache|The request path attached to a forwarding rule

 |
|└VServerGroupId|String|rsp-6cejjzlld7|The ID of the destination VServer group bound to a forwarding rule

 |
|└Cookie|String|23|The Cookie configured on the server

 It can contain 1 to 200 characters, including only ASCII letters and numbers. It cannot contain commas \(,\), semicolons \(;\), or spaces or start with a dollar sign \($\).

 **Note:** This parameter is mandatory and takes effect when **StickySession** is set to **on** and **StickySessionType** is set to **server**.

 |
|└CookieTimeout|Integer|56|Cookie expiration period Valid values: **1 to 86400** \(seconds\)

 **Note:** This parameter takes effect when **StickySession** is set to **on** and **StickySessionType** is set to **insert**.

 |
|└HealthCheck|String|off|Whether to enable health checks

 Valid values: **on | off**

 **Note:** This parameter takes effect when **ListenerSync** is set to **off**. Listener settings prevail when this parameter is set to **on**.

 |
|└HealthCheckConnectPort|Integer|45|The port of the backend server used for health checks.

 Valid values: **1–65535**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**. By default, backend listener settings prevail if this parameter retains empty and **HealthCheck** is set to **on**.

 |
|└HealthCheckDomain|String|domain|The domain name used for health checks. Valid values:

 -   **$\_ip**: private IP address of the backend server.

When the IP address is specified or this parameter is not specified, SLB uses the private IP addresses of backend servers as the domain names for health checks.

 -   **domain**: domain name, which must be 1 to 80 characters in length and can contain letters, numbers, periods \(.\), and hyphens \(-\).

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|└HealthCheckHttpCode|String|http\_3xx|The HTTP status code indicating that the health check is normal. Separate multiple status codes by commas. Default value: **http\_2xx**.

 Valid values: **http\_2xx | http\_3xx | http\_4xx | http\_5xx**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|└HealthCheckInterval|Integer|5|Time interval between two health checks

 Valid values: **1–50** \(seconds\)

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|└HealthCheckTimeout|Integer|34|The amount of time to wait for the response from a health check. If the backend ECS instance does not send a correct response in the specified time, the health check fails.

 Valid values: **1–300** \(seconds\)

 **Note:** If the value of **HealthCheckTimeout**is smaller than that of **HealthCheckInterval**, the parameter **HealthCHeckTimeout** is invalid, and the timeout is set to the value of **HealthCheckInterval**. This parameter takes effect when **HealthCheck** is set to **on**.

 |
|└HealthCheckURI|String|/example|The URI used for health checks.

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|└HealthyThreshold|Integer|5|The number of consecutive successes of health checks before a backend server is declared as healthy \(from **failure** to **success**\).

 Valid values: **2–10**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |
|└ListenerSync|String|off|Whether a forwarding rule inherits the settings of a health check, session persistence, and scheduling algorithm from a listener

 Valid values: **on | off**

 -   **off**: The rule customs health check and session persistence settings instead of inheriting them.
-   **on**: The rule inherits the settings from the listener.

 |
|└Scheduler|String|wrr|Scheduling algorithm. Valid values:

 -   **wrr** \(default value\): A backend server with a higher weight is more likely to be polled.
-   **wlc**: A backend server with a higher weight will receive more requests. When the weight is the same, the server with a smaller number of connections is more likely to be polled.
-   **rr**: Requests are evenly and sequentially distributed to the backend servers.

 **Note:** This parameter takes effect when **ListenerSync** is set to **off**. Listener settings prevail when this parameter is set to **on**.

 |
|└StickySession|String|off|Whether to enable session persistence

 Valid values: **on | off**

 **Note:** This parameter takes effect when **ListenerSync** is set to **off**. Listener settings prevail when this parameter is set to **on**.

 |
|└StickySessionType|String|insert|The method used to handle the Cookie. Valid values:

 -   **insert**: Insert the Cookie. When a client accesses SLB for the first time, SLB inserts Cookies into response requests \(that is, SLB inserts SERVERID into the HTTP/HTTPS response data packets\). The next time the client accesses SLB with the Cookies, SLB will direct and forward the requests to the previously recorded backend server.
-   **server**: Rewrite the Cookie. SLB will overwrite the original cookie whena new cookie is set. The next time the client carries the new cookie to access the SLB instance, the listener will distribute the request to the previously recorded backend server.

 **Note:** This parameter takes effect when **StickySession** is set to **on**.

 |
|└UnhealthyThreshold|Integer|2|The number of consecutive failures of health checks before a backend server is declared as unhealthy \(from **success** to **failure**\).

 Valid values: **2–10**

 **Note:** This parameter takes effect when **HealthCheck** is set to **on**.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeRules
&ListenerPort=90
&LoadBalancerId=lb-bp1ca0zt07t934wxezyxo
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeRulesResponse>
  <RequestId>11D87D83-741B-4F8A-8AAD-FD6867FDE7B2</RequestId>
  <Rules>
    <Rule>
      <Url>/image</Url>
      <Domain>example.com</Domain>
      <VServerGroupId>rsp-bp114nimo4kl9</VServerGroupId>
      <RuleId>rule-bp1supbxos2u3</RuleId>
      <RuleName>auto_named_rule</RuleName>
      <ListenerSync>on</ListenerSync>
    </Rule>
    <Rule>
      <Domain>test.com</Domain>
      <VServerGroupId>rsp-bp114nimo4kl9</VServerGroupId>
      <RuleId>rule-bp1efemp9suk5</RuleId>
      <RuleName>Rule2</RuleName>
      <ListenerSync>on</ListenerSync>
    </Rule>
    <Rule>
      <Domain>test2.com</Domain>
      <VServerGroupId>rsp-bp114nimo4kl9</VServerGroupId>
      <RuleId>rule-bp12jzy0hvio3</RuleId>
      <RuleName>Rule3</RuleName>
      <ListenerSync>on</ListenerSync>
    </Rule>
  </Rules>
</DescribeRulesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"11D87D83-741B-4F8A-8AAD-FD6867FDE7B2",
	"Rules":{
		"Rule":[
			{
				"Domain":"example.com",
				"Url":"/image",
				"RuleId":"rule-bp1supbxos2u3",
				"VServerGroupId":"rsp-bp114nimo4kl9",
				"RuleName":"auto_named_rule",
				"ListenerSync":"on"
			},
			{
				"Domain":"test.com",
				"RuleId":"rule-bp1efemp9suk5",
				"VServerGroupId":"rsp-bp114nimo4kl9",
				"RuleName":"Rule2",
				"ListenerSync":"on"
			},
			{
				"Domain":"test2.com",
				"RuleId":"rule-bp12jzy0hvio3",
				"VServerGroupId":"rsp-bp114nimo4kl9",
				"RuleName":"Rule3",
				"ListenerSync":"on"
			}
		]
	}
}
```

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

