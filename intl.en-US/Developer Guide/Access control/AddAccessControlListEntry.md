# AddAccessControlListEntry {#doc_api_876093 .reference}

You can call the AddAccessControlListEntry API to add IP addresses to an access control policy group.

Each group can contain multiple IP addresses or CIDR blocks. Access control policy groups are subject to the following limits:

-   Each Alibaba Cloud account can add a maximum of 50 IP addresses at a time.
-   An access control policy group can contain a maximum of 300 items.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=AddAccessControlListEntry) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|AddAccessControlListEntry|The action to perform. Valid value: **AddAccessControlListEntry**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs

 |
|AclEntrys|String|No|\[\{"entry":"10.0.0.0/24","comment":"privaterule1"\},\{"entry":"192.168.0.0/16","comment":"privaterule2"\}\]|The IP address to be added to the access control policy group. You can specify the target IP addresses or IP address segments \(namely, CIDR blocks\). Use commas \(,\) to separate multiple IP addresses or CIDR blocks.

 **Note:** You can add a maximum of 50 IP address or CIDR blocks at a time.

 |
|AclId|String|No|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|988CB45E-1643-48C0-87B4-928DDF77EA4|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=AddAccessControlListEntry
&RegionId=cn-hangzhou
&AclEntrys=[{"entry":"10.0.0.0/24","comment":"privaterule1"},{"entry":"192.168.0.0/16","comment":"privaterule2"}]
&AclId=acl-bp1l0kk4gxce43kzet04s
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<AddAccessControlListEntryResponse>
  <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
</AddAccessControlListEntryResponse>

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

