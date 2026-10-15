# WhoisFreaks.Api.DNSApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DnsBulk**](DNSApi.md#dnsbulk) | **POST** /v2.0/dns/bulk/live | Bulk DNS Lookup |
| [**DnsHistorical**](DNSApi.md#dnshistorical) | **GET** /v2.0/dns/historical | Historical DNS Lookup |
| [**DnsLive**](DNSApi.md#dnslive) | **GET** /v2.0/dns/live | Live DNS Lookup |
| [**DnsReverse**](DNSApi.md#dnsreverse) | **GET** /v2.1/dns/reverse | Reverse DNS Lookup |

<a id="dnsbulk"></a>
# **DnsBulk**
> BulkDnsResponse DnsBulk (string type, DnsBulkRequest dnsBulkRequest, string? format = null)

Bulk DNS Lookup

Up to 100 domains + 100 IPs in one request.

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
    public class DnsBulkExample
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
            var apiInstance = new DNSApi(httpClient, config, httpClientHandler);
            var type = "A,MX,TXT";  // string |  (default to "all")
            var dnsBulkRequest = new DnsBulkRequest(); // DnsBulkRequest | 
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Bulk DNS Lookup
                BulkDnsResponse result = apiInstance.DnsBulk(type, dnsBulkRequest, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DNSApi.DnsBulk: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DnsBulkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk DNS Lookup
    ApiResponse<BulkDnsResponse> response = apiInstance.DnsBulkWithHttpInfo(type, dnsBulkRequest, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DNSApi.DnsBulkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **type** | **string** |  | [default to &quot;all&quot;] |
| **dnsBulkRequest** | [**DnsBulkRequest**](DnsBulkRequest.md) |  |  |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**BulkDnsResponse**](BulkDnsResponse.md)

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

<a id="dnshistorical"></a>
# **DnsHistorical**
> HistoricalDnsResponse DnsHistorical (string domainName, string type, int? page = null, string? format = null)

Historical DNS Lookup

All historical DNS records. 2 credits per page (100 records/page).

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
    public class DnsHistoricalExample
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
            var apiInstance = new DNSApi(httpClient, config, httpClientHandler);
            var domainName = "whoisfreaks.com";  // string | 
            var type = "A,MX,TXT";  // string |  (default to "all")
            var page = 1;  // int? |  (optional)  (default to 1)
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Historical DNS Lookup
                HistoricalDnsResponse result = apiInstance.DnsHistorical(domainName, type, page, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DNSApi.DnsHistorical: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DnsHistoricalWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Historical DNS Lookup
    ApiResponse<HistoricalDnsResponse> response = apiInstance.DnsHistoricalWithHttpInfo(domainName, type, page, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DNSApi.DnsHistoricalWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domainName** | **string** |  |  |
| **type** | **string** |  | [default to &quot;all&quot;] |
| **page** | **int?** |  | [optional] [default to 1] |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**HistoricalDnsResponse**](HistoricalDnsResponse.md)

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

<a id="dnslive"></a>
# **DnsLive**
> DnsResponse DnsLive (string type, string? domainName = null, string? ipAddress = null, string? format = null)

Live DNS Lookup

Real-time DNS record lookup. 1 credit per query.

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
    public class DnsLiveExample
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
            var apiInstance = new DNSApi(httpClient, config, httpClientHandler);
            var type = "A,MX,TXT";  // string | all or comma-separated: A,MX,NS,TXT,SOA,SPF,AAAA,CNAME (default to "all")
            var domainName = "whoisfreaks.com";  // string? |  (optional) 
            var ipAddress = "8.8.8.8";  // string? | Use for PTR lookups (optional) 
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Live DNS Lookup
                DnsResponse result = apiInstance.DnsLive(type, domainName, ipAddress, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DNSApi.DnsLive: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DnsLiveWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Live DNS Lookup
    ApiResponse<DnsResponse> response = apiInstance.DnsLiveWithHttpInfo(type, domainName, ipAddress, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DNSApi.DnsLiveWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **type** | **string** | all or comma-separated: A,MX,NS,TXT,SOA,SPF,AAAA,CNAME | [default to &quot;all&quot;] |
| **domainName** | **string?** |  | [optional]  |
| **ipAddress** | **string?** | Use for PTR lookups | [optional]  |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**DnsResponse**](DnsResponse.md)

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
| **429** | Too many requests |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="dnsreverse"></a>
# **DnsReverse**
> ReverseDnsResponse DnsReverse (string value, string type, bool? exact = null, int? page = null, string? format = null)

Reverse DNS Lookup

Search domains by IP or DNS value. 5 credits per page.

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
    public class DnsReverseExample
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
            var apiInstance = new DNSApi(httpClient, config, httpClientHandler);
            var value = "8.8.8.8";  // string | IP, CIDR, or record value
            var type = "a";  // string | 
            var exact = true;  // bool? |  (optional)  (default to true)
            var page = 1;  // int? |  (optional)  (default to 1)
            var format = "json";  // string? |  (optional)  (default to json)

            try
            {
                // Reverse DNS Lookup
                ReverseDnsResponse result = apiInstance.DnsReverse(value, type, exact, page, format);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DNSApi.DnsReverse: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DnsReverseWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reverse DNS Lookup
    ApiResponse<ReverseDnsResponse> response = apiInstance.DnsReverseWithHttpInfo(value, type, exact, page, format);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DNSApi.DnsReverseWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **value** | **string** | IP, CIDR, or record value |  |
| **type** | **string** |  |  |
| **exact** | **bool?** |  | [optional] [default to true] |
| **page** | **int?** |  | [optional] [default to 1] |
| **format** | **string?** |  | [optional] [default to json] |

### Return type

[**ReverseDnsResponse**](ReverseDnsResponse.md)

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

