# RemoveBackendServers {#doc_api_874453 .reference}

You can call the RemoveBackendServers API to remove backend servers.

**Note:** If the ECS instance to be removed does not exist in the specified backend server group, the action is ignored and no error will be returned.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=RemoveBackendServers) to debug in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|RemoveBackendServers|The action to perform. Valid value: **RemoveBackendServers**

 |
|BackendServers|String|Yes|\["vm-233","vm-234"\]|The backend servers to be removed.

 **Note:** Up to 20 backend servers can be removed at a time.

 |
|LoadBalancerId|String|Yes|lb-bp1qjwo61pqz3ahltv0mw|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-east-hangzhou-01|The ID of the region to which the SLB instance belongs

 |
|OwnerAccount|String|No|OwnerAccount|The ID of the account

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|LoadBalancerId|String|139a00604ad-cn-east-hangzhou-01|The ID of the SLB instance

 |
|BackendServers| | |A list of backend servers

 |
|└Description|String|Backend servers|A description of the backend server group

 |
|└ServerId|String|vm-232|The backend server name ID, which is the ECS instance ID.

 |
|└Type|String|ecs|The backend server type. Valid values:

 -   **ecs**: ECS instance \(default\)
-   **eni**: Elastic Network Interface \(ENI\)

 |
|└Weight|Integer|100|The weight of the backend server. Valid values: **0–100**.

 |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=RemoveBackendServers
&BackendServers=["vm-233","vm-234"]
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<RemoveBackendServersResponse>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
  <LoadBalancerId>139a00604ad-cn-east-hangzhou-01</LoadBalancerId>
  <BackendServers>
    <BackendServer>
      <ServerId>vm-231</ServerId>
      <Weight>100</Weight>
    </BackendServer>
    <BackendServer>
      <ServerId>vm-232</ServerId>
      <Weight>100</Weight>
    </BackendServer>
  </BackendServers>
</RemoveBackendServersResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"BackendServers":{
		"BackendServer":[
			{
				"ServerId":"vm-233",
				"Weight":100
			},
			{
				"ServerId":"vm-234",
				"Weight":100
			}
		]
	},
	"RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710",
	"LoadBalancerId":"139a00604ad-cn-east-hangzhou-01"
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

