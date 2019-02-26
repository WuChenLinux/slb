# SetLoadBalancerName {#doc_api_844520 .reference}

You can call the SetLoadBalancerName API to modify the name of an SLB instance.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=SetLoadBalancerName) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|SetLoadBalancerName|The action to perform. Valid value: **SetLoadBalancerName**

 |
|LoadBalancerId|String|Yes|lb-bp1b6c719dfa08exfuca5|The ID of the SLB instance

 |
|LoadBalancerName|String|Yes|abc1|The name of the SLB instance.

 The name must be 2 to 128 characters in length and can contain letters, numbers, Chinese characters, underscores \(\_\), periods \(.\), and hyphens \(-\). It must start with a letter or Chinese character.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs.

 You can query the region ID by referring to the list of [regions and zones](~~40654~~) or by calling the [DescribeRegions](~~25609~~) API.

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://slb.aliyuncs.com/?Action=SetLoadBalancerName
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&LoadBalancerName=abc
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<SetLoadBalancerStatusResponse>
  <RequestId>3C7F675E-9F82-4806-BA47-FF57E3ACC850</RequestId>
</SetLoadBalancerStatusResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"3C7F675E-9F82-4806-BA47-FF57E3ACC850"
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

