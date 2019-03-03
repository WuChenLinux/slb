# Multiple-zone deployment {#concept_i55_h4n_vdb .concept}

You can create SLB instances in a region with multiple zones to improve the availability.

## What is multiple-zone deployment? {#section_blw_bxt_vdb .section}

A cloud product zone refers to a set of independent infrastructures. Different zones have independent infrastructures \(such as network, power supply and air-conditioning\), thus an infrastructure fault in one zone does not affect other zones.

To provide more reliable services, SLB has deployed multiple zones in most regions to achieve disaster recovery across data centers. When the data center in the primary zone is faulty and unavailable, SLB is able to switch to the data center in the backup zone to restore its service capabilities within 30 seconds.

Note the following about SLB primary/backup zones:

-   SLB supports attaching ECS instances in different zones as long as the ECS instances and the SLB instance are in the same region. SLB can distribute traffic to the ECS instances in different zones.
-   Normally, the SLB instance in the backup zone is in the standby state. You cannot manually switch the primary/backup state of an SLB instance. SLB switches to the backup zone only when the whole primary zone is unavailable due to data center outage or exit cable failure and more. SLB will not switch to the backup zone if only one instance in the primary zone is faulty.
-   SLB and ECS instances are deployed in different clusters. When an SLB instance in Zone A is unavailable, the ECS instances in Zone A are not necessarily unavailable. Therefore, after SLB switches to the backup zone, the SLB instance in the backup zone still can distribute traffic to the added ECS instances. However, if all clusters in a zone is unavailable or the optical cable is faulty, all services \(including but not limited to SLB instances and ECS instances\) in the zone cannot work anymore.

For more information, see [SLB high availability](../reseller.en-US/Product Introduction/High availability of Server Load Balancer.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4155/15516088602835_en-US.png)

## Primary/backup zone list {#section_ml2_ykb_wdb .section}

The following table lists the primary/backup zones in different regions. You can call the DescribeZones API to obtain available primary/backup zones in a region.

|Region|Zone type|Zones|
|:-----|:--------|:----|
|China \(Hangzhou\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone B|Zone DZone G

|
|Zone D|Zone E|
|Zone E|Zone DZone F

|
|Zone F|Zone E|
|Zone G|Zone BZone H

|
|Zone H|Zone G|
|China \(Shanghai\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone AZone C

Zone D

|
|Zone C|Zone B|
|Zone D|Zone BZone E

|
|Zone E|Zone DZone F

|
|Zone F|Zone E|
|China \(Shenzhen\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone AZone C

|
|Zone C|Zone BZone D

|
|Zone D|Zone CZone E

|
|Zone E|Zone D|
|China \(Qingdao\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone B|Zone C|
|Zone C|Zone B|
|China \(Beijing\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone BZone D

Zone E

|
|Zone B|Zone C|
|Zone C|Zone E|
|Zone D|Zone A|
|Zone E|Zone CZone F

|
|Zone F|Zone EZone G

|
|Zone G|Zone F|
|China \(Zhangjiakou\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|China \(Hohhot\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|Germany \(Frankfurt\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|UK \(London\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|UAE \(Dubai\)|Single-zone|Zone A|
|Singapore|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|Zone C|Zone B|
|Australia \(Sydney\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|Malaysia \(Kuala Lumpur\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|Indonesia \(Jakarta\)|Single-zone|Zone A|
|India \(Mumbai\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|Japan \(Tokyo\)|Single-zone|Zone A|
|Hong Kong|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone B|Zone C|
|Zone C|Zone B|
|US \(Virginia\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|
|US \(Silicon Valley\)|Multiple-zone|**Primary zone**|**Available backup zones**|
|Zone A|Zone B|
|Zone B|Zone A|

