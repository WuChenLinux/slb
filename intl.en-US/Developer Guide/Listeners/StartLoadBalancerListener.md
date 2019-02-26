# StartLoadBalancerListener {#doc_api_881517 .reference}

You can call the StartLoadBalancerListener API to start a listener.

Start a listener

Before you call this API, note the following:

-   The API can be called only when the listener is in stopped status.
-   After this API is called successfully, the status of the listener changes to starting.
-   If the status of the SLB instance to which the listener belongs is locked, this API cannot be called.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=StartLoadBalancerListener) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|StartLoadBalancerListener|The action to perform. Valid value: **StartLoadBalancerListener**

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance. Valid values: 1–65535

 |
|LoadBalancerId|String|Yes|lb-bp13jaf5qli5xmgl1miup|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the SLB instance belongs.

 You can query the region ID by calling the [DescribeRegions](~~27584~~) API.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=StartLoadBalancerListener
&ListenerPort=80
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<StartLoadBalancerListenerResponse>
  <RequestId>CC000321-00F2-49B8-9BCA-60D822414960</RequestId>
</StartLoadBalancerListenerResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"CC000321-00F2-49B8-9BCA-60D822414960"
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

