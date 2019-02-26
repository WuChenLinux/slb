# SetAccessControlListAttribute {#doc_api_859278 .reference}

You can call the SetAccessControlListAttribute API to modify the name of an access control policy group.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetAccessControlListAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetAccessControlListAttribute|The action to perform. Valid value: **SetAccessControlListAttribute**.

 |
|AclId|String|Yes|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group

 |
|AclName|String|Yes|test1|The name of the access control policy group

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|AclId|String|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group

 |
|RequestId|String|988CB45E-1643-48C0-87B4-928DDF77EA49|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=SetAccessControlListAttribute
&AclId=acl-bp1l0kk4gxce43kzet04s
&AclName=test1
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetAccessControlListAttributeResponse>
  <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
</SetAccessControlListAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"988CB45E-1643-48C0-87B4-928DDF77EA49"
}
```

Error response example

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

