# DescribeDomainExtensions {#doc_api_834974 .reference}

You can call the DescribeDomainExtensions API to query the added domain name extensions.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeDomainExtensions) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeDomainExtensions|The action to perform. Valid value: **DescribeDomainExtensions**

 |
|ListenerPort|Integer|Yes|443|The frontend port used by the HTTPS listener of the SLB instance. Valid values: **1–65535**

 |
|LoadBalancerId|String|Yes|lb-bp1o94dp5i6earr9g6d1l|The ID of the SLB instance

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the SLB instance belongs

 |
|DomainExtensionId|String|No|de-bp1rp7ta191dv|The ID of the domain name extension

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|DomainExtensions| | |A list of domain name extensions

 |
|└Domain|String|www.example.com|The domain name

 |
|└DomainExtensionId|String|de-bp1rp7ta191dv|The ID of the domain name extension

 |
|└ServerCertificateId|String|1231579085529123\_166f8204689\_1714763408\_709981430|The ID of the certificate used by the domain name

 |
|RequestId|String|48C1B671-C6DB-4DDE-9B30-10557E36CDE0|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? ListenerPort=443
&LoadBalancerId=lb-bp1o94dp5i6earr9g6d1l
&RegionId=cn-hangzhou
&Action=DescribeDomainExtensions
&DomainExtensionId=de-bp1rp7ta191dv
&Tags={"tagKey":"Key1","tagValue":"Value1"}
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeDomainExtensionsResponse>
  <RequestId>CCC710F8-285C-415F-9211-9BD6BF7BB997</RequestId>
  <DomainExtensions>
    <DomainExtension>
      <ServerCertificateId>1231579085529123_164b57543a9_464232488_760347667</ServerCertificateId>
      <Domain>*.example2.com</Domain>
      <DomainExtensionId>de-bp1k4chwdnhxd</DomainExtensionId>
    </DomainExtension>
  </DomainExtensions>
</DescribeDomainExtensionsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"48C1B671-C6DB-4DDE-9B30-10557E36CDE0",
	"DomainExtensions":{
		"DomainExtension":[
			{
				"ServerCertificateId":"1231579085529123_166f8204689_1714763408_709981430",
				"Domain":"*.example1.com",
				"DomainExtensionId":"de-bp1rp7ta191dv"
			}
		]
	}
}
```

Error response example

## Error codes { .section}

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

