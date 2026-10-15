# WhoisFreaks.Model.BulkDomainAvailabilityRequest
Request body for POST /v2.0/domain/availability. Use domainNames OR tld.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**DomainNames** | **List&lt;string&gt;** | Mode 1: list of full domain names. Cannot be used with tld. | [optional] 
**Tld** | **List&lt;string&gt;** | Mode 2: TLDs to check against the domain query param. Cannot be used with domainNames. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

