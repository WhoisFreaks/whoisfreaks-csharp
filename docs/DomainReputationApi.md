# WhoisFreaks.Api.DomainReputationApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DomainReputation**](DomainReputationApi.md#domainreputation) | **GET** /v1/domain/security | Domain Reputation Lookup |

<a id="domainreputation"></a>
# **DomainReputation**
> DomainReputationResponse DomainReputation (string domainName, string? format = null)

Domain Reputation Lookup

Real-time domain threat assessment. Returns risk verdict, trust score, DGA analysis, threat intelligence matches, and security signals. 1 credit.

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
    public class DomainReputationExample
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
            var apiInstance = new DomainReputationApi(httpClient, config, httpClientHandler);
            var domainName = "amazon.com";  // string | The domain name to assess
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Domain Reputation Lookup
                DomainReputationResponse result = apiInstance.DomainReputation(domainName, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DomainReputationApi.DomainReputation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DomainReputationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Domain Reputation Lookup
    ApiResponse<DomainReputationResponse> response = apiInstance.DomainReputationWithHttpInfo(domainName, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DomainReputationApi.DomainReputationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domainName** | **string** | The domain name to assess |  |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**DomainReputationResponse**](DomainReputationResponse.md)

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
| **404** | Not found |  -  |
| **429** | Too many requests |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

