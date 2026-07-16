# WhoisFreaks.Api.TyposquattingApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**Typosquatting**](TyposquattingApi.md#typosquatting) | **GET** /v3.0/domain/typos | Typosquatting Lookup |

<a id="typosquatting"></a>
# **Typosquatting**
> TyposquattingResponse Typosquatting (string? keyword = null, string? pattern = null, string? pageToken = null)

Typosquatting Lookup

Find typo variants of a brand. 5 credits per page.

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
    public class TyposquattingExample
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
            var apiInstance = new TyposquattingApi(httpClient, config, httpClientHandler);
            var keyword = "keyword_example";  // string? |  (optional) 
            var pattern = "pattern_example";  // string? |  (optional) 
            var pageToken = "pageToken_example";  // string? |  (optional) 

            try
            {
                // Typosquatting Lookup
                TyposquattingResponse result = apiInstance.Typosquatting(keyword, pattern, pageToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TyposquattingApi.Typosquatting: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the TyposquattingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Typosquatting Lookup
    ApiResponse<TyposquattingResponse> response = apiInstance.TyposquattingWithHttpInfo(keyword, pattern, pageToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TyposquattingApi.TyposquattingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyword** | **string?** |  | [optional]  |
| **pattern** | **string?** |  | [optional]  |
| **pageToken** | **string?** |  | [optional]  |

### Return type

[**TyposquattingResponse**](TyposquattingResponse.md)

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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

