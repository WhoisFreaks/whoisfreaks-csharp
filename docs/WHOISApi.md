# WhoisFreaks.Api.WHOISApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkWhois**](WHOISApi.md#bulkwhois) | **POST** /v2.0/bulkwhois/live | Bulk WHOIS Lookup |
| [**WhoisHistory**](WHOISApi.md#whoishistory) | **GET** /v2.0/whois/history | Historical WHOIS records for a domain |
| [**WhoisLive**](WHOISApi.md#whoislive) | **GET** /v2.0/whois/live | Live WHOIS Lookup |
| [**WhoisReverse**](WHOISApi.md#whoisreverse) | **GET** /v2.0/whois/reverse | Reverse WHOIS lookup by keyword |

<a id="bulkwhois"></a>
# **BulkWhois**
> BulkWhoisResponse BulkWhois (BulkWhoisRequest bulkWhoisRequest, string? format = null)

Bulk WHOIS Lookup

Up to 100 domains in one request. 1 credit per successful domain.

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
    public class BulkWhoisExample
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
            var apiInstance = new WHOISApi(httpClient, config, httpClientHandler);
            var bulkWhoisRequest = new BulkWhoisRequest(); // BulkWhoisRequest | 
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Bulk WHOIS Lookup
                BulkWhoisResponse result = apiInstance.BulkWhois(bulkWhoisRequest, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WHOISApi.BulkWhois: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkWhoisWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk WHOIS Lookup
    ApiResponse<BulkWhoisResponse> response = apiInstance.BulkWhoisWithHttpInfo(bulkWhoisRequest, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WHOISApi.BulkWhoisWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkWhoisRequest** | [**BulkWhoisRequest**](BulkWhoisRequest.md) |  |  |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**BulkWhoisResponse**](BulkWhoisResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful response |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="whoishistory"></a>
# **WhoisHistory**
> WhoisHistoricalResponse WhoisHistory (string domainName, int? page = null, string? format = null)

Historical WHOIS records for a domain

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
    public class WhoisHistoryExample
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
            var apiInstance = new WHOISApi(httpClient, config, httpClientHandler);
            var domainName = "domainName_example";  // string | Domain to fetch historical WHOIS records for
            var page = 56;  // int? | Page number (optional) 
            var format = "json";  // string? |  (optional) 

            try
            {
                // Historical WHOIS records for a domain
                WhoisHistoricalResponse result = apiInstance.WhoisHistory(domainName, page, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WHOISApi.WhoisHistory: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WhoisHistoryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Historical WHOIS records for a domain
    ApiResponse<WhoisHistoricalResponse> response = apiInstance.WhoisHistoryWithHttpInfo(domainName, page, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WHOISApi.WhoisHistoryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domainName** | **string** | Domain to fetch historical WHOIS records for |  |
| **page** | **int?** | Page number | [optional]  |
| **format** | **string?** |  | [optional]  |

### Return type

[**WhoisHistoricalResponse**](WhoisHistoricalResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Historical WHOIS records |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="whoislive"></a>
# **WhoisLive**
> WhoisResponse WhoisLive (string domainName, string? format = null)

Live WHOIS Lookup

Real-time WHOIS lookup from authoritative servers. Cost 1 credit.

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
    public class WhoisLiveExample
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
            var apiInstance = new WHOISApi(httpClient, config, httpClientHandler);
            var domainName = whoisfreaks.com;  // string | 
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Live WHOIS Lookup
                WhoisResponse result = apiInstance.WhoisLive(domainName, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WHOISApi.WhoisLive: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WhoisLiveWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Live WHOIS Lookup
    ApiResponse<WhoisResponse> response = apiInstance.WhoisLiveWithHttpInfo(domainName, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WHOISApi.WhoisLiveWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domainName** | **string** |  |  |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**WhoisResponse**](WhoisResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful response |  -  |
| **401** | Invalid API key |  -  |
| **404** | Not found |  -  |
| **429** | Too many requests |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="whoisreverse"></a>
# **WhoisReverse**
> ReverseWhoisResponse WhoisReverse (string keyword, int? page = null, string? format = null)

Reverse WHOIS lookup by keyword

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
    public class WhoisReverseExample
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
            var apiInstance = new WHOISApi(httpClient, config, httpClientHandler);
            var keyword = "keyword_example";  // string | Keyword to search across WHOIS records
            var page = 56;  // int? | Page number (optional) 
            var format = "json";  // string? |  (optional) 

            try
            {
                // Reverse WHOIS lookup by keyword
                ReverseWhoisResponse result = apiInstance.WhoisReverse(keyword, page, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WHOISApi.WhoisReverse: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WhoisReverseWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reverse WHOIS lookup by keyword
    ApiResponse<ReverseWhoisResponse> response = apiInstance.WhoisReverseWithHttpInfo(keyword, page, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WHOISApi.WhoisReverseWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyword** | **string** | Keyword to search across WHOIS records |  |
| **page** | **int?** | Page number | [optional]  |
| **format** | **string?** |  | [optional]  |

### Return type

[**ReverseWhoisResponse**](ReverseWhoisResponse.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reverse WHOIS results (paginated) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

