# SetBackendServers {#doc_api_834981 .reference}

You can call the SetBackendServers API to set the weights of backend severs.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetBackendServers) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetBackendServers|The action to perform. Valid value: **SetBackendServers**

 |
|BackendServers|String|Yes|\[\{"ServerId":"vm-233","Weight":"0"\},\{"ServerId":"vm-234","Weight":"0"\}\]|The list of backend servers to be added.

 **Note:** Only backend servers \(ECS instances\) in running status can be added. You can add up to 20 backend servers at a time.

 |
|LoadBalancerId|String|Yes|lb-bp1qjwo61pqz3ahltv0mw|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|LoadBalancerId|String|139a00604ad-cn-east-hangzhou-01|The ID of the SLB instance

 |
|BackendServers| | |A list of backend servers

 |
|└ServerId|String|vm-234|The ID of the ECS instance

 |
|└Weight|String|100|The weight of the backend server

 |
|└Description|String|Backend server|A description of the backend server

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

/? Action=SetBackendServers
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<AddBackendServersResponse>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
  <LoadBalancerId>139a00604ad-cn-east-hangzhou-01</LoadBalancerId>
  <BackendServers>
    <BackendServer>
      <ServerId>vm-233</ServerId>
      <Weight>0</Weight>
    </BackendServer>
    <BackendServer>
      <ServerId>vm-234</ServerId>
      <Weight>0</Weight>
    </BackendServer>
  </BackendServers>
</AddBackendServersResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"AddBackendServersResponse":{
		"BackendServers":{
			"BackendServer":[
				{
					"ServerId":"vm-233",
					"Weight":"0"
				},
				{
					"ServerId":"vm-234",
					"Weight":"0"
				}
			]
		},
		"RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710",
		"LoadBalancerId":"139a00604ad-cn-east-hangzhou-01"
	}
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

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

