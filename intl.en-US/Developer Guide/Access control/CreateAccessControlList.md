# CreateAccessControlList {#doc_api_876090 .reference}

You can call the CreateAccessControlList API to create an access control policy group.

You can create multiple access control policy groups. Each group can contain multiple IP addresses or CIDR blocks. Access control policy groups are subject to the following limits:

-   Each Alibaba Cloud account can create a maximum of 50 access control policy groups per region.
-   Each Alibaba Cloud account can add a maximum of 50 IP addresses at a time.
-   Each access control policy group can contain a maximum of 300 items.
-   Each listener can be attached with a maximum of 50 access control policy groups.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=CreateAccessControlList) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|CreateAccessControlList|The action to perform. Valid value: **CreateAccessControlList**

 |
|AclName|String|Yes|rule1|The name of the access control policy group

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs

 |
|AddressIPVersion|String|No|ipv4|The IP version, which can be set to ipv4 or ipv6.

 **Note:** Currently, only zones E and F in the China \(Hangzhou\) region and zones F and G in the China \(Beijing\) region support ipv6 performance-guaranteed instances.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|AclId|String|acl-rj9xpxzcwxrukois65yw3|The ID of the access control policy group

 |
|RequestId|String|988CB45E-1643-48C0-87B4-928DDF77EA49|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=CreateAccessControlList
&AclName=rule1
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<CreateAccessControlListResponse>
  <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
  <AclId>acl-rj9xpxzcwxrukois65yw3</AclId>
</CreateAccessControlListResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"AclId":"acl-rj9xpxzcwxrukois65yw3",
	"RequestId":"988CB45E-1643-48C0-87B4-928DDF77EA49"
}
```

Error response example

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

