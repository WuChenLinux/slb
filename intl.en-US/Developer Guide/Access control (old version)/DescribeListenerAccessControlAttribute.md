# DescribeListenerAccessControlAttribute {#doc_api_876096 .reference}

You can call the DescribeListenerAccessControlAttribute API to query the whitelist settings of a specific listener.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeListenerAccessControlAttribute) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeListenerAccessControlAttribute|The action to perform. Valid value: **DescribeListenerAccessControlAttribute**.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can refer to the [region and zone](~~40654~~) list or call the [DescribeRegions](~~25609~~) API to query this parameter.

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: 1–65535

 |
|LoadBalancerId|String|Yes|lb-8vb86hxixo8lvsja86jaz|The ID of the SLB instance

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|AccessControlStatus|String|open\_white\_list|Whether to enable access control.

 -   **open\_white\_list**: Enable a whitelist for access control.
-   **close**: Disable access control.

 |
|SourceItems|String|1.1.1.1,1.1.1.0/24|The access control list

 |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DescribeListenerAccessControlAttribute
&ListenerPort=80
&LoadBalancerId=lb-8vb86hxixo8lvsja86jaz
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeListenerAccessControlAttributeResponse>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
  <AccessControlStatus>open_white_list</AccessControlStatus>
  <SourceItems>1.1.1.1,1.1.1.0/24</SourceItems>
</DescribeListenerAccessControlAttributeResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710",
	"SourceItems":"1.1.1.1,1.1.1.0/24",
	"AccessControlStatus":"open_white_list"
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

