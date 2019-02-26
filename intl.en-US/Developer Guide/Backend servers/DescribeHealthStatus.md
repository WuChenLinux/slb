# DescribeHealthStatus {#doc_api_879477 .reference}

You can call the DescribeHealthStatus API to query the health status of a backend server.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeHealthStatus) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeHealthStatus|The action to perform. Valid value: **DescribeHealthStatus**

 |
|LoadBalancerId|String|Yes|lb-bp1qjwo61pqz3ahltv0mw|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |
|ListenerPort|Integer|No|80|The frontend port used by the SLB instance.

 Valid values: **1–65535**

 **Note:** If you do not set this parameter, the health check status of all ports is returned.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|BackendServers| | |A list of backend servers

 |
|└ServerId|String|vm-234|The ECS instance ID or ENI ID

 |
|└ServerHealthStatus|String|abnormal|The health status of a backend server:

 -   **normal**: The backend server is healthy.
-   **abnormal**: The backend server is unhealthy.
-   **unavailable**: The health check is not completed.

 |
|└EniHost|String|192.168.0.1|The IP address of the ENI

 |
|└ListenerPort|Integer|80|The frontend port used by the SLB instance

 |
|└Port|Integer|70|The backend port used by the SLB instance

 |
|└ServerIp|String|192.168.0.2|The IP address of the ECS instance

 |
|└Type|String|ecs|The backend server type. Valid values:

 -   **ecs**: ECS instance \(default\)
-   **eni**: Elastic Network Interface \(ENI\)

 |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeHealthStatus
&LoadBalancerId=lb-bp1qjwo61pqz3ahltv0mw
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeHealthStatusResponse>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
  <BackendServers>
    <BackendServer>
      <ServerId>vm-233</ServerId>
      <ServerHealthStatus>normal</ServerHealthStatus>
    </BackendServer>
    <BackendServer>
      <ServerId>vm-234</ServerId>
      <ServerHealthStatus>abnormal</ServerHealthStatus>
    </BackendServer>
  </BackendServers>
</DescribeHealthStatusResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"196EC328-B566-4226-B435-8697723205EF",
	"BackendServers":{
		"BackendServer":[
			{
				"ServerId":"i-bp1do02x7n4nua4k72um",
				"ServerHealthStatus":"abnormal",
				"Port":80,
				"ListenerPort":443
			}
		]
	}
}
```

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

