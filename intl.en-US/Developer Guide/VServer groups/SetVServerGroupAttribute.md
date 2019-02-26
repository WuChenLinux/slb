# SetVServerGroupAttribute {#doc_api_879380 .reference}

You can call the SetVServerGroupAttribute API to modify the configurations of a VServer group.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetVServerGroupAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetVServerGroupAttribute|The action to perform. Valid value: **SetVServerGroupAttribute**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |
|VServerGroupId|String|Yes|rsp-cige6j5e7p|The ID of the VServer group

 |
|BackendServers|String|No|\[\{'ServerId':'vm-233','Port':'80','Weight':'100'\},\{'ServerId':'vm-232','Port':'90','Weight':'100'\},\{'ServerId':'vm-231','Port':'70','Weight':'100'\}\]|The list of the backend servers in the VServer group.

 A VServer group can contain up to 20 backend servers.

 |
|VServerGroupName|String|No|Group1|The name of the VServer group. Here, you can edit the name of the VServer group as needed.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|VServerGroupId|String|rsp-cige6j5e7p|The ID of the VServer group

 |
|VServerGroupName|String|Group1|The name of the VServer group

 |
|BackendServers| | |A list of backend servers

 |
|└ServerId|String|vm-231|The ECS instance ID or ENI ID

 |
|└Port|Integer|70|The port used by the backend server

 |
|└Weight|Integer|100|The weight of the backend server

 |
|└Description|String|A description of the VServer group|A description of the VServer group

 |
|└Type|String|ecs|The backend server type. Valid values:

 -   **ecs**: ECS instance \(default\)
-   **eni**: Elastic Network Interface \(ENI\)

 |
|RequestId|String|9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=SetVServerGroupAttribute
&RegionId=cn-hangzhou
&VServerGroupId=rsp-cige6j5e7p
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetVServerGroupAttribute>
  <RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
  <VServerGroupId>rsp-cige6j5e7p</VServerGroupId>
  <VServerGroupName>Group1</VServerGroupName>
  <BackendServers>
    <BackendServer>
      <ServerId>vm-233</ServerId>
      <Port>80</Port>
      <Weight>100</Weight>
    </BackendServer>
    <BackendServer>
      <ServerId>vm-232</ServerId>
      <Port>90</Port>
      <Weight>100</Weight>
    </BackendServer>
    <BackendServer>
      <ServerId>vm-231</ServerId>
      <Port>70</Port>
      <Weight>100</Weight>
    </BackendServer>
  </BackendServers>
</SetVServerGroupAttribute>

```

`JSON` format

``` {#json_return_success_demo}
{
	"BackendServers":{
		"BackendServer":[
			{
				"ServerId":"vm-233",
				"Port":"80",
				"Weight":"100"
			},
			{
				"ServerId":"vm-232",
				"Port":"90",
				"Weight":"100"
			},
			{
				"ServerId":"vm-231",
				"Port":"70",
				"Weight":"100"
			}
		]
	},
	"RequestId":"9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C",
	"VServerGroupId":"rsp-cige6j5e7p",
	"VServerGroupName":"Group1"
}
```

## Error codes { .section}

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|The VServerGroupName or BackendServers is required at lease one.|The parameter HealthCheckTimeout is a required parameter.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

