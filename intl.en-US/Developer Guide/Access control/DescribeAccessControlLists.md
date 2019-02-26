# DescribeAccessControlLists {#doc_api_859273 .reference}

You can call the DescribeAccessControlLists API to query created access control policy groups.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeAccessControlLists) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeAccessControlLists|The action to perform. Valid value: **DescribeAccessControlLists**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |
|AclName|String|No|rule1|The name of the access control policy group

 |
|AddressIPVersion|String|No|ipv4|IP address type of the instance attached to the access control policy group Valid values:

 -   **ipv4**: The IP address type of the SLB instance is IPv4.
-   **ipv6**: The IP address type of the SLB instance is IPv6.

 |
|PageNumber|Integer|No|1|The page number of the access control policy group. Default value: 1.

 |
|PageSize|Integer|No|10|The number of rows per page for a paged query. Maximum value: 50. Default value: 10.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|Acls| | |A list of access control policy groups that are queried

 |
|└AclId|String|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group

 |
|└AclName|String|rule1|The name of the access control policy group

 |
|└AddressIPVersion|String|ipv4|IP address type of the associated SLB instance

 |
|RequestId|String|B646EF-6147-4566|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=DescribeAccessControlLists
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeAccessControlListsResponse>
  <RequestId>3CB646EF-6147-4566-A9D9-CE8FBE86F971</RequestId>
  <Acls>
    <Acl>
      <AclId>acl-bp1j9vn2g7wm9wn0xassu</AclId>
      <AclName>test</AclName>
      <AddressIPVersion>ipv4</AddressIPVersion>
    </Acl>
    <Acl>
      <AclId>acl-bp1l0kk4gxce43kzet04s</AclId>
      <AclName>doctest</AclName>
      <AddressIPVersion>ipv4</AddressIPVersion>
    </Acl>
  </Acls>
</DescribeAccessControlListsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"3CB646EF-6147-4566-A9D9-CE8FBE86F971",
	"Acls":{
		"Acl":[
			{
				"AclId":"acl-bp1j9vn2g7wm9wn0xassu",
				"AclName":"test",
				"AddressIPVersion":"ipv4"
			},
			{
				"AclId":"acl-bp1l0kk4gxce43kzet04s",
				"AclName":"doctest",
				"AddressIPVersion":"ipv4"
			}
		]
	}
}
```

Error response example

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

