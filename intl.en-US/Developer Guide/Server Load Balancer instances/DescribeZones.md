# DescribeZones {#doc_api_844515 .reference}

You can call the DescribeZones API to query the zones in a region.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeZones) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeZones|The action to perform. Valid value: **DescribeZones**

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region

 |
|OwnerAccount|String|No|OwnerAccount|OwnerAccount

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|Zones| | |A list of available zones

 |
|└ZoneId|String|cn-hangzhou-b|The ID of the zone

 |
|└LocalName|String|China East 1 Zone B|The name of the zone

 |
|└SlaveZones| | |The list of standby zones

 |
|└ZoneId|String|cn-hangzhou-g|The ID of the standby zone

 |
|└LocalName|String|East China 1 Zone G|The name of the standby zone

 |
|RequestId|String|A48D35FF-440A-4BC0-A4A2-A9BF69B7E43A|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

/? Action=DescribeZones
&RegionId=cn-beijing
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeZonesResponse>
  <RequestId>3FF183FF-F4AA-40E8-8B5D-90788C6799C2</RequestId>
  <Zones>
    <Zone>
      <SlaveZones>
        <SlaveZone>
          <ZoneId>cn-hangzhou-g</ZoneId>
          <LocalName>China East 1 Zone G</LocalName>
        </SlaveZone>
        <SlaveZone>
          <ZoneId>cn-hangzhou-d</ZoneId>
          <LocalName>China East 1 Zone D</LocalName>
        </SlaveZone>
      </SlaveZones>
      <ZoneId>cn-hangzhou-b</ZoneId>
      <LocalName>China East 1 Zone B</LocalName>
    </Zone>
    <Zone>
      <SlaveZones>
        <SlaveZone>
          <ZoneId>cn-hangzhou-e</ZoneId>
          <LocalName>China East 1 Zone E</LocalName>
        </SlaveZone>
      </SlaveZones>
      <ZoneId>cn-hangzhou-d</ZoneId>
      <LocalName>China East 1 Zone D</LocalName>
    </Zone>
    <Zone>
      <SlaveZones>
        <SlaveZone>
          <ZoneId>cn-hangzhou-f</ZoneId>
          <LocalName>China East 1 Zone F</LocalName>
        </SlaveZone>
        <SlaveZone>
          <ZoneId>cn-hangzhou-d</ZoneId>
          <LocalName>China East 1 Zone D</LocalName>
        </SlaveZone>
      </SlaveZones>
      <ZoneId>cn-hangzhou-e</ZoneId>
      <LocalName>China East 1 Zone E</LocalName>
    </Zone>
    <Zone>
      <SlaveZones>
        <SlaveZone>
          <ZoneId>cn-hangzhou-e</ZoneId>
          <LocalName>China East 1 Zone E</LocalName>
        </SlaveZone>
      </SlaveZones>
      <ZoneId>cn-hangzhou-f</ZoneId>
      <LocalName>China East 1 Zone F</LocalName>
    </Zone>
    <Zone>
      <SlaveZones>
        <SlaveZone>
          <ZoneId>cn-hangzhou-h</ZoneId>
          <LocalName>China East 1 Zone H</LocalName>
        </SlaveZone>
        <SlaveZone>
          <ZoneId>cn-hangzhou-b</ZoneId>
          <LocalName>China East 1 Zone B</LocalName>
        </SlaveZone>
      </SlaveZones>
      <ZoneId>cn-hangzhou-g</ZoneId>
      <LocalName>China East 1 Zone G</LocalName>
    </Zone>
    <Zone>
      <SlaveZones>
        <SlaveZone>
          <ZoneId>cn-hangzhou-g</ZoneId>
          <LocalName>China East 1 Zone G</LocalName>
        </SlaveZone>
      </SlaveZones>
      <ZoneId>cn-hangzhou-h</ZoneId>
      <LocalName>China East 1 Zone H</LocalName>
    </Zone>
  </Zones>
</DescribeZonesResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"3FF183FF-F4AA-40E8-8B5D-90788C6799C2",
	"Zones":{
		"Zone":[
			{
				"ZoneId":"cn-hangzhou-b",
				"SlaveZones":{
					"SlaveZone":[
						{
							"ZoneId":"cn-hangzhou-g",
							"LocalName":"China East 1 Zone G"
						},
						{
							"ZoneId":"cn-hangzhou-d",
							"LocalName":"China East 1 Zone D"
						}
					]
				},
				"LocalName":"China East 1 Zone B"
			},
			{
				"ZoneId":"cn-hangzhou-d",
				"SlaveZones":{
					"SlaveZone":[
						{
							"ZoneId":"cn-hangzhou-e",
							"LocalName":"China East 1 Zone E"
						}
					]
				},
				"LocalName":"China East 1 Zone D"
			},
			{
				"ZoneId":"cn-hangzhou-e",
				"SlaveZones":{
					"SlaveZone":[
						{
							"ZoneId":"cn-hangzhou-f",
							"LocalName":"China East 1 Zone F"
						},
						{
							"ZoneId":"cn-hangzhou-d",
							"LocalName":"China East 1 Zone D"
						}
					]
				},
				"LocalName":"China East 1 Zone E"
			},
			{
				"ZoneId":"cn-hangzhou-f",
				"SlaveZones":{
					"SlaveZone":[
						{
							"ZoneId":"cn-hangzhou-e",
							"LocalName":"China East 1 Zone E"
						}
					]
				},
				"LocalName":"China East 1 Zone F"
			},
			{
				"ZoneId":"cn-hangzhou-g",
				"SlaveZones":{
					"SlaveZone":[
						{
							"ZoneId":"cn-hangzhou-h",
							"LocalName":"China East 1 Zone H"
						},
						{
							"ZoneId":"cn-hangzhou-b",
							"LocalName":"China East 1 Zone B"
						}
					]
				},
				"LocalName":"China East 1 Zone G"
			},
			{
				"ZoneId":"cn-hangzhou-h",
				"SlaveZones":{
					"SlaveZone":[
						{
							"ZoneId":"cn-hangzhou-g",
							"LocalName":"China East 1 Zone G"
						}
					]
				},
				"LocalName":"China East 1 Zone H"
			}
		]
	}
}
```

Error response examples

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

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidParameter| |The parameter Bandwidth is invalid. Please check that the parameter is correct.|
|400|InvalidParameter|Illegal parameter, query.namespace is not auth.|The parameter Bandwidth is invalid. Please check that the parameter is correct.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

