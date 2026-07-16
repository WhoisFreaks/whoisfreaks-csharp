# WhoisFreaks.Api.SubdomainsApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**Subdomains**](SubdomainsApi.md#subdomains) | **GET** /v1.0/subdomains | Subdomains Lookup |

<a id="subdomains"></a>
# **Subdomains**
> SubdomainsResponse Subdomains (string domain, DateOnly? after = null, DateOnly? before = null, string? status = null, int? page = null, string? format = null)

Subdomains Lookup

All subdomains including nested. 2 credits per query.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using WhoisFreaks.Api;
using WhoisFreaks.Client;
using WhoisFreaks.Model;

namespace Example
{
    public class SubdomainsExample
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
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new SubdomainsApi(httpClient, config, httpClientHandler);
            var domain = "domain_example";  // string | 
            var after = DateOnly.Parse("2013-10-20");  // DateOnly? |  (optional) 
            var before = DateOnly.Parse("2013-10-20");  // DateOnly? |  (optional) 
            var status = "active";  // string? |  (optional) 
            var page = 1;  // int? |  (optional)  (default to 1)
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Subdomains Lookup
                SubdomainsResponse result = apiInstance.Subdomains(domain, after, before, status, page, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SubdomainsApi.Subdomains: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SubdomainsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Subdomains Lookup
    ApiResponse<SubdomainsResponse> response = apiInstance.SubdomainsWithHttpInfo(domain, after, before, status, page, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SubdomainsApi.SubdomainsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |
| **after** | **DateOnly?** |  | [optional]  |
| **before** | **DateOnly?** |  | [optional]  |
| **status** | **string?** |  | [optional]  |
| **page** | **int?** |  | [optional] [default to 1] |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**SubdomainsResponse**](SubdomainsResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful response |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

