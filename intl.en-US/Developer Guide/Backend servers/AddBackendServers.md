# AddBackendServers {#doc_api_903362 .reference}

You can call the AddBackendServers API to add backend servers.

**Note:** If the same ECS instances are added in a request, only the first ECS instance will be added.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=AddBackendServers) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|AddBackendServers|The action to perform. Valid value: **AddBackendServers**

 |
|BackendServers|String|Yes|\[\{"ServerId":"i-2zej4lxhjoq1icue6kup","Weight":"100"\},\{"ServerId":"i-2ze1u9ywulp5pbvvc7hv","Weight":"100"\}\]|The list of backend servers to be added.

 **Note:** Only backend servers \(ECS instances\) in running status can be added. You can add up to 20 backend servers at a time.

 |
|LoadBalancerId|String|Yes|lb-2ze7o5h52g02kkzze7lru|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-beijing|The region to which the SLB instance belongs.

 You can query the region ID by calling the [DescribeRegions](~~27584~~) API.

 |
|OwnerAccount|String|No|OwnerAccount|OwnerAccount

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|LoadBalancerId|String|lb-2ze7o5h52g02kkzze7lru|The ID of the SLB instance

 |
|BackendServers| | |A list of backend servers

 |
|└ServerId|String|i-2zej4lxhjoq1icue6kup|The ECS instance ID or ENI instance ID

 |
|└Weight|String|100|The weight of the backend server

 |
|└Description|String|Backend server|A description of the backend server

 |
|└Type|String|ecs|The backend server type

 |
|RequestId|String|34B82C81-F13B-4EEB-99F6-A048C67CC830|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=AddBackendServers
&LoadBalancerId=lb-2ze7o5h52g02kkzze7lru
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<AddBackendServersResponse>
  <BackendServers>
    <BackendServer>
      <ServerId>i-2zej4lxhjoq1icue6kup</ServerId>
      <Weight>100</Weight>
      <Type>ecs</Type>
    </BackendServer>
    <BackendServer>
      <ServerId>i-2ze1u9ywulp5pbvvc7hv</ServerId>
      <Weight>100</Weight>
      <Type>ecs</Type>
    </BackendServer>
  </BackendServers>
  <RequestId>34B82C81-F13B-4EEB-99F6-A048C67CC830</RequestId>
  <LoadBalancerId>lb-2ze7o5h52g02kkzze7lru</LoadBalancerId>
</AddBackendServersResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"34B82C81-F13B-4EEB-99F6-A048C67CC830",
	"BackendServers":{
		"BackendServer":[
			{
				"ServerId":"i-2zej4lxhjoq1icue6kup",
				"Weight":100,
				"Type":"ecs"
			},
			{
				"ServerId":"i-2ze1u9ywulp5pbvvc7hv",
				"Weight":100,
				"Type":"ecs"
			}
		]
	},
	"LoadBalancerId":"lb-2ze7o5h52g02kkzze7lru"
}
```

## Error codes { .section}

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidParameter|The specified load balancer does not support the network type of the ECS instance.|SLB instances do not support ECS instances of this network type. Please change the ECS network type and try again.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

