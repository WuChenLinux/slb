# RemoveTags {#doc_api_834936 .reference}

You can call the RemoveTags API to remove tags that are attached to an SLB instance.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=RemoveTags) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|RemoveTags|The action to perform. Valid value: **RemoveTags**

 |
|LoadBalancerId|String|Yes|139a00604ad-cn-east-hangzhou-01|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |
|Tags|String|Yes|\[\{"TagKey":"Key1","TagValue":"Value1"\}\{"TagKey":"Key2","TagValue":"Value2"\}\]|A list of tags to be removed.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=RemoveTags
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&RegionId=cn-hangzhou
&Tags=[{"TagKey":"Key1","TagValue":"Value1"}{"TagKey":"Key2","TagValue":"Value2"}]
&<Common request parameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<RemoveTagsResponse>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
</RemoveTagsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710"
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

