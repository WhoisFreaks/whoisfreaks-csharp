# WhoisFreaks.Model.DnsRecord
Union of all DNS record variants (A/AAAA/MX/NS/CNAME/PTR/TXT/SPF/SOA).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **int** | Numeric DNS record type: 1 A, 2 NS, 5 CNAME, 6 SOA, 12 PTR, 15 MX, 16 TXT, 28 AAAA, 99 SPF. | [optional] 
**DnsType** | **string** | Record type name, e.g. A, MX, TXT | [optional] 
**Name** | **string** |  | [optional] 
**Ttl** | **int** |  | [optional] 
**RawText** | **string** | The record in zone-file format | [optional] 
**RRsetType** | **int** |  | [optional] 
**SingleName** | **string** | Target host for NS, CNAME and PTR records | [optional] 
**Address** | **string** |  | [optional] 
**Priority** | **int** |  | [optional] 
**Exchange** | **string** |  | [optional] 
**Target** | **string** |  | [optional] 
**Strings** | **List&lt;string&gt;** |  | [optional] 
**Host** | **string** |  | [optional] 
**Admin** | **string** |  | [optional] 
**Serial** | **long** | SOA serial; values above 2^31 are common, so it is 64-bit | [optional] 
**Refresh** | **int** |  | [optional] 
**Retry** | **int** |  | [optional] 
**Expire** | **int** |  | [optional] 
**Minimum** | **int** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

