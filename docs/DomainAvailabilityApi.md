# WhoisFreaks.Api.DomainAvailabilityApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkDomainAvailabilityV2**](DomainAvailabilityApi.md#bulkdomainavailabilityv2) | **POST** /v2.0/domain/availability | Bulk Domain Availability Check |
| [**DomainAvailabilityV2**](DomainAvailabilityApi.md#domainavailabilityv2) | **GET** /v2.0/domain/availability | Domain Availability Check with Suggestions |

<a id="bulkdomainavailabilityv2"></a>
# **BulkDomainAvailabilityV2**
> BulkDomainAvailabilityResponse BulkDomainAvailabilityV2 (BulkDomainAvailabilityRequest bulkDomainAvailabilityRequest, string? domain = null, string? format = null)

Bulk Domain Availability Check

Two bulk modes. Mode 1: POST domainNames array. Mode 2: POST tld array plus domain query param. Max 100 domains per request. 1 credit per domain checked.

### Example
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using WhoisFreaks.Api;
using WhoisFreaks.Client;
using WhoisFreaks.Model;

namespace Example
{
    public class BulkDomainAvailabilityV2Example
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.whoisfreaks.com";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("apiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("apiKey", "Bearer");

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            HttpClient httpClient = new HttpClient(httpClientHandler);
            var apiInstance = new DomainAvailabilityApi(httpClient, config, httpClientHandler);
            var bulkDomainAvailabilityRequest = new BulkDomainAvailabilityRequest(); // BulkDomainAvailabilityRequest | 
            var domain = "google.com";  // string? | Required for TLD-mode bulk check (base domain). (optional) 
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Bulk Domain Availability Check
                BulkDomainAvailabilityResponse result = apiInstance.BulkDomainAvailabilityV2(bulkDomainAvailabilityRequest, domain, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DomainAvailabilityApi.BulkDomainAvailabilityV2: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkDomainAvailabilityV2WithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk Domain Availability Check
    ApiResponse<BulkDomainAvailabilityResponse> response = apiInstance.BulkDomainAvailabilityV2WithHttpInfo(bulkDomainAvailabilityRequest, domain, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DomainAvailabilityApi.BulkDomainAvailabilityV2WithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkDomainAvailabilityRequest** | [**BulkDomainAvailabilityRequest**](BulkDomainAvailabilityRequest.md) |  |  |
| **domain** | **string?** | Required for TLD-mode bulk check (base domain). | [optional]  |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**BulkDomainAvailabilityResponse**](BulkDomainAvailabilityResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful response |  -  |
| **400** | Bad request |  -  |
| **401** | Invalid API key |  -  |
| **429** | Too many requests |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="domainavailabilityv2"></a>
# **DomainAvailabilityV2**
> DomainAvailabilityResponse DomainAvailabilityV2 (string domain, bool? sug = null, int? count = null, string? format = null)

Domain Availability Check with Suggestions

Check availability of a single domain and optionally get suggestions across multiple TLDs. 1 credit per domain checked. sug=false checks only the queried domain; sug=true returns up to `count` (max 100) TLD suggestions.

### Example
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using WhoisFreaks.Api;
using WhoisFreaks.Client;
using WhoisFreaks.Model;

namespace Example
{
    public class DomainAvailabilityV2Example
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.whoisfreaks.com";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("apiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("apiKey", "Bearer");

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            HttpClient httpClient = new HttpClient(httpClientHandler);
            var apiInstance = new DomainAvailabilityApi(httpClient, config, httpClientHandler);
            var domain = "google.com";  // string | The domain name to check
            var sug = false;  // bool? | Whether to return TLD suggestions alongside the queried domain. (optional)  (default to false)
            var count = 5;  // int? | Number of TLD suggestions to return when sug=true. Maximum is 100. (optional)  (default to 5)
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Domain Availability Check with Suggestions
                DomainAvailabilityResponse result = apiInstance.DomainAvailabilityV2(domain, sug, count, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DomainAvailabilityApi.DomainAvailabilityV2: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DomainAvailabilityV2WithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Domain Availability Check with Suggestions
    ApiResponse<DomainAvailabilityResponse> response = apiInstance.DomainAvailabilityV2WithHttpInfo(domain, sug, count, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DomainAvailabilityApi.DomainAvailabilityV2WithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** | The domain name to check |  |
| **sug** | **bool?** | Whether to return TLD suggestions alongside the queried domain. | [optional] [default to false] |
| **count** | **int?** | Number of TLD suggestions to return when sug&#x3D;true. Maximum is 100. | [optional] [default to 5] |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**DomainAvailabilityResponse**](DomainAvailabilityResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful response |  -  |
| **400** | Bad request |  -  |
| **401** | Invalid API key |  -  |
| **429** | Too many requests |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

