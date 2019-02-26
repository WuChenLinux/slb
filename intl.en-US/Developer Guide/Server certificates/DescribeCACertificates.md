# DescribeCACertificates {#doc_api_834969 .reference}

You can call the DescribeCACertificates API to query the details of CA certificates.

**Note:** For security reasons, only the name and the fingerprint are returned instead of the certificate content and the private key.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeCACertificates) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeCACertificates|The action to perform. Valid value: **DescribeCACertificates**.

 |
|RegionId|String|Yes|cn-hangzhou|The region to which the CA certificate belongs.

 You can query the region ID by calling the [DescribeRegions](~~27584~~) API.

 |
|CACertificateId|String|No|139a00604bd-cn-east-hangzhou-02|The ID of the CA certificate

 |
|OwnerAccount|String|No|testuser@aliyun.com|Your account

 |
|ResourceGroupId|String|No|rg-atstuj3rtoptyui|The ID of the enterprise resource group

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|CACertificates| | |The CA certificate information

 |
|└CACertificateId|String|139a00604bd-cn-east-hangzhou-02|The ID of the CA certificate

 |
|└CACertificateName|String|test|The name of the CA certificate

 |
|└RegionId|String|cn-hangzhou|The region to which the CA certificate belongs

 |
|└Fingerprint|String|AC:BE:FD|The fingerprint of the CA certificate

 |
|└CommonName|String|.example.com|The domain name of the CA certificate

 |
|└CreateTime|String|2017-08-31T02:49:05Z|The time at which the CA certificate is created

 |
|└CreateTimeStamp|Long|1504147745000|The timestamp that indicates when the CA certificate is created

 |
|└ExpireTime|String|2024-11-21T06:04:25Z|The time at which the CA certificate expires

 |
|└ExpireTimeStamp|Long|1732169065000|The timestamp that indicates when the CA certificate expires

 |
|└ResourceGroupId|String|rg-atstuj3rtoptyui|The ID of the enterprise resource group

 |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? RegionId=cn-hangzhou
&Action=DescribeCACertificates
&RegionId=cn-hangzhou
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeCACertificateResponse>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
  <CACertificates>
    <CACertificate>
      <CACertificateId>139a00604bd-cn-east-hangzhou-01
        </CACertificateId>
      <CACertificateName>bcd
    </CACertificateName>
      <Fingerprint>AB:CB:DE</Fingerprint>
    </CACertificate>
    <CACertificate>
      <CACertificateId>139a00604bd-cn-east-hangzhou-02</CACertificateId>
      <CACertificateName>cde</CACertificateName>
      <Fingerprint>AC:BE:FD</Fingerprint>
    </CACertificate>
  </CACertificates>
</DescribeCACertificateResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710",
	" CACertificates":{
		"CACertificate":[
			{
				"CACertificateName":"bcd",
				"Fingerprint ":"AB:CB:DE",
				"CACertificateId":"139a00604bd-cn-east-hangzhou-01"
			},
			{
				"CACertificateName":"cde",
				"Fingerprint ":"AC:BE:FD",
				"CACertificateId":"282b00102ac-cn-east-hangzhou-02"
			}
		]
	}
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

