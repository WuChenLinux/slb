# DeleteDomainExtension {#doc_api_880890 .reference}

You can call the DeleteDomainExtension API to delete a domain name extension.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DeleteDomainExtension) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DeleteDomainExtension|The action to perform. Valid value: **DeleteDomainExtension**

 |
|DomainExtensionId|String|Yes|de-bp1rp7ta191dv|The ID of the domain name extension to be deleted

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|RequestId|String|149A2470-F010-4437-BF68-343D5099C19D|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? DomainExtensionId=de-bp1rp7ta191dv
&RegionId=cn-hangzhou
&Action=DeleteDomainExtension
&Tags={"tagKey":"Key1","tagValue":"Value1"}
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DeleteDomainExtensionResponse>
  <RequestId>149A2470-F010-4437-BF68-343D5099C19D</RequestId>
</DeleteDomainExtensionResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"5B45BED9-4D41-47B0-ADD6-47A5624516C7"
}
```

Error response example

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

