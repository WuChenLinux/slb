# AddListenerWhiteListItem {#doc_api_884836 .reference}

You can call the AddListenerWhiteListItem API to add IP addresses or CIDR blocks to a listener whitelist.

## Debug {#apiExplorer .section}

Perform a [debug](https://api.aliyun.com/#product=Slb&api=AddVServerGroupBackendServers) in OpenAPI Explorer. We recommend that you use OpenAPI Explorer. By using OpenAPI Explorer, you can call APIs, generate SDK code examples automatically, and search APIs, allowing you to quickly and easily get started with using APIs on the cloud.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|AddListenerWhiteListItem|The action to perform. Valid value: AddListenerWhiteListItem

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance

 |
|LoadBalancerId|String|Yes|139a00604ad-cn-east-hangzhou-01|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |
|SourceItems|String|Yes|1.1.1.1,1.1.1.0/21|Access control list.

 This parameter takes effect when AccessControlStatus of the listener is set to open\_white\_list.

 Both IP addresses and IP address segments \(namely, CIDR blocks\) are supported. Use commas \(,\) to separate multiple IP addresses or CIDR blocks.

 0.0.0.0 or 0.0.0.0/0 is not allowed. You can call the [SetListenerAccessControlStatus](~~27599~~) API to set AccessControlStatus to close to disable access control.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=AddListenerWhiteListItem
&ListenerPort=80
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&SourceItems=1.1.1.1,1.1.1.0/21
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<AddListenerWhiteListItemResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</AddListenerWhiteListItemResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
}
```

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

