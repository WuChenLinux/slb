# DeleteMasterSlaveServerGroup {#doc_api_834970 .reference}

You can call the DeleteMasterSlaveServerGroup API to delete a specified active/standby server group.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DeleteMasterSlaveServerGroup) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DeleteMasterSlaveServerGroup|The action to perform. Valid value: **DeleteMasterSlaveServerGroup**

 |
|MasterSlaveServerGroupId|String|Yes|rsp-cige6j5e7p|The ID of the active/standby server group.

 **Attention**:

 An active/standby server group in use cannot be deleted.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? MasterSlaveServerGroupId=rsp-cige6j5e7p
&RegionId=cn-hangzhou
&Action=DeleteMasterSlaveServerServerGroup
&Tags={"tagKey":"Key1","tagValue":"Value1"}
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteMasterSlaveServerGroupResponse>
  <RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
</DeleteMasterSlaveServerGroupResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C"
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

