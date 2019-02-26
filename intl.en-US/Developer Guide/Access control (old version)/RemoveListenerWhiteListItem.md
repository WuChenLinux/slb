# RemoveListenerWhiteListItem {#doc_api_834942 .reference}

You can call the RemoveListenerWhiteListItem API to delete IP addresses from a listener whitelist.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=RemoveListenerWhiteListItem) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|RemoveListenerWhiteListItem|The action to perform. Valid value: **RemoveListenerWhiteListItem**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can call the [DescribeRegions](~~27584~~)API to query the region ID.

 |
|ListenerPort|Integer|Yes|80|The action to perform. Valid value: **RemoveListenerWhiteListItem**.

 |
|LoadBalancerId|String|Yes|lb-8vb86hxixo8lvsja86jaz|The ID of the SLB instance

 |
|SourceItems|String|Yes|1.1.1.1|The access control list. Both IP addresses and IP address segments \(namely, CIDR blocks\) are supported. Use commas \(,\) to separate multiple IP addresses or CIDR blocks.

 **Note**: If all IP addresses or CIDR blocks are deleted, the listener is inaccessible.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=RemoveListenerWhiteListItem
&ListenerPort=80
&LoadBalancerId=lb-8vb86hxixo8lvsja86jaz
&SourceItems=1.1.1.1
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<RemoveListenerWhiteListItemResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</RemoveListenerWhiteListItemResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
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

