# DescribeAccessControlListAttribute {#doc_api_859274 .reference}

You can call the DescribeAccessControlListAttribute API to query the settings of a specified access control policy group.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeAccessControlListAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeAccessControlListAttribute|The action to perform. Valid value: **DescribeAccessControlListAttribute**.

 |
|AclId|String|Yes|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group to be queried

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the access control policy group belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |
|AclEntryComment|String|No|test|A comment on an item in the access control policy group

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|AclEntrys| | |A list of information about the access control policy group

 |
|└AclEntryComment|String|Access control items|A comment on the access control item

 |
|└AclEntryIP|String|192.168.0.1|The IP address of the access control item

 |
|AclId|String|acl-bp1l0kk4gxce43kzet04s|The ID of the access control policy group

 |
|AclName|String|doctest|The name of the access control policy group

 |
|AddressIPVersion|String|ipv4|The IP address type of the associated SLB instance

 |
|RelatedListeners| | |A list of listeners that are attached to the access control policy group

 |
|└AclType|String|white|Access control type:

 -   **black**: blacklist
-   **white**: whitelist

 |
|└ListenerPort|Integer|443|The frontend port of the listener that is attached to the access control policy group

 |
|└LoadBalancerId|String|lb-bp13jaf5qli5xmgl1miup|The ID of the SLB instance

 |
|└Protocol|String|https|The protocol type of the listener that is attached to the access control policy group

 |
|RequestId|String|C9906A1D-86F7-4C9C-A369-54DA42EF206A|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=DescribeAccessControlListAttribute
&AclId=acl-bp1l0kk4gxce43kzet04s
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeAccessControlListAttributeResponse>
  <AclId>acl-bp1l0kk4gxce43kzet04s</AclId>
  <RelatedListeners>
    <RelatedListener>
      <AclType>white</AclType>
      <LoadBalancerId>lb-bp13jaf5qli5xmgl1miup</LoadBalancerId>
      <Protocol>https</Protocol>
      <ListenerPort>443</ListenerPort>
    </RelatedListener>
  </RelatedListeners>
  <AclName>doctest</AclName>
  <RequestId>C9906A1D-86F7-4C9C-A369-54DA42EF206A</RequestId>
  <AddressIPVersion>ipv4</AddressIPVersion>
</DescribeAccessControlListAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"AclId":"acl-bp1l0kk4gxce43kzet04s",
	"RequestId":"C9906A1D-86F7-4C9C-A369-54DA42EF206A",
	"AclName":"doctest",
	"RelatedListeners":{
		"RelatedListener":[
			{
				"AclType":"white",
				"LoadBalancerId":"lb-bp13jaf5qli5xmgl1miup",
				"Protocol":"https",
				"ListenerPort":443
			}
		]
	},
	"AddressIPVersion":"ipv4"
}
```

Error response example

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

