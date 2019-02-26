# SetListenerAccessControlStatus {#doc_api_883991 .reference}

You can call the SetListenerAccessControlStatus API to determine whether to enable a whitelist for access control for a specified listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetListenerAccessControlStatus) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetListenerAccessControlStatus|The action to perform. Valid value: **SetListenerAccessControlStatus**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can call the [DescribeRegions](~~27584~~) API to query this parameter.

 |
|AccessControlStatus|String|Yes|open\_white\_list|Whether to enable access control. Valid values:

 -   **open\_white\_list**: Enable a whitelist for access control.
-   **close**: Disable access control.

 **Note**: If you do not set a whitelist after enabling access control, SLB is inaccessible.

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-8vb86hxixo8lvsja86jaz|The ID of the SLB instance

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=SetListenerAccessControlStatus
&AccessControlStatus=open_white_list
&ListenerPort=80
&LoadBalancerId=lb-8vb86hxixo8lvsja86jaz
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetListenerAccessControlStatusResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</SetListenerAccessControlStatusResponse>

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

