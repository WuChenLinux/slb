# DeleteLoadBalancerListener {#doc_api_874462 .reference}

You can call the DeleteLoadBalancerListener API to delete a listener.

**Note:** Only a listener in **stopped** or **running** status can be deleted.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DeleteLoadBalancerListener) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DeleteLoadBalancerListener|The action to perform. Valid value: **Deleteloadbalancerlistener**

 |
|ListenerPort|Integer|Yes|80|The frontend port used by the SLB instance.

 Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp13jaf5qli5xmgl1miup|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=DeleteLoadBalancerListener
&ListenerPort=80
&LoadBalancerId=lb-bp13jaf5qli5xmgl1miup
&<Common Parameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteLoadBalancerListenerResponse>
  <RequestId>791D8B68-AE0F-4174-AF54-088C8B3C5D54</RequestId>
</DeleteLoadBalancerListenerResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"791D8B68-AE0F-4174-AF54-088C8B3C5D54"
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

