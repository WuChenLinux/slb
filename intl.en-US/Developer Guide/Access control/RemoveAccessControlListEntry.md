# RemoveAccessControlListEntry {#doc_api_859285 .reference}

You can call the RemoveAccessControlListEntry API to delete IP addresses or CIDR blocks from an access control policy group.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=RemoveAccessControlListEntry) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|RemoveAccessControlListEntry|The action to perform. Valid value: **RemoveAccessControlListEntry**.

 |
|AclId|String|Yes|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |
|AclEntrys|String|No|\[\{"entry":"10.0.0.0/24","comment":"privaterule1"\}\]|The IP address to be added to the access control policy group. You can specify the target IP addresses or IP address segments \(namely, CIDR blocks\). Use commas \(,\) to separate multiple IP addresses or CIDR blocks.

 **Note**: If the access control policy group is attached to a listener, the IP addresses or CIDR blocks in the group cannot be deleted.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|988CB45E-1643-48C0-87B4-928DDF77EA49|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=RemoveAccessControlListEntry
&AclId=acl-bp1l0kk4gxce43kzet04s
&RegionId=cn-hangzhou
&AclEntrys=[{"entry":"10.0.0.0/24","comment":"privaterule1"}]
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<RemoveAccessControlListEntryResponse>
  <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
</RemoveAccessControlListEntryResponse>

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

