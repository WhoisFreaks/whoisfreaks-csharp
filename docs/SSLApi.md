# WhoisFreaks.Api.SSLApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**SslLookup**](SSLApi.md#ssllookup) | **GET** /v1.0/ssl/live | SSL Certificate Lookup |

<a id="ssllookup"></a>
# **SslLookup**
> SslResponse SslLookup (string domainName, bool? chain = null, bool? sslRaw = null, string? format = null)

SSL Certificate Lookup

Real-time SSL cert with optional chain.

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
    public class SslLookupExample
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
            var apiInstance = new SSLApi(httpClient, config, httpClientHandler);
            var domainName = "domainName_example";  // string | 
            var chain = false;  // bool? |  (optional)  (default to false)
            var sslRaw = false;  // bool? |  (optional)  (default to false)
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // SSL Certificate Lookup
                SslResponse result = apiInstance.SslLookup(domainName, chain, sslRaw, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SSLApi.SslLookup: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SslLookupWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // SSL Certificate Lookup
    ApiResponse<SslResponse> response = apiInstance.SslLookupWithHttpInfo(domainName, chain, sslRaw, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SSLApi.SslLookupWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domainName** | **string** |  |  |
| **chain** | **bool?** |  | [optional] [default to false] |
| **sslRaw** | **bool?** |  | [optional] [default to false] |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**SslResponse**](SslResponse.md)

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

