# DeleteAccessControlList {#doc_api_881525 .reference}

You can call the DeleteAccessControlList API to delete access control policy groups.

**Note:** An access control policy group can be deleted only after it is detached from a listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DeleteAccessControlList) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DeleteAccessControlList|The action to perform. Valid value: **DeleteAccessControlList**.

 |
|AclId|String|Yes|acl-bp1l0kk4gxce43kzet04s|The ID of an access control policy group

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|988CB45E-1643-48C0-87B4-928DDF77EA49|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=DeleteAccessControlList
&AclId=acl-bp1l0kk4gxce43kzet04s
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteAccessControlListResponse>
  <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
</DeleteAccessControlListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"988CB45E-1643-48C0-87B4-928DDF77EA49"
}
```

Error response examples

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

