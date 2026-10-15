# WhoisFreaks.Api.DatabasesDNSApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DbDnsDaily**](DatabasesDNSApi.md#dbdnsdaily) | **GET** /v3.2/download/dbupdate/daily/dns | DNS Database Daily |
| [**DbDnsMonthly**](DatabasesDNSApi.md#dbdnsmonthly) | **GET** /v3.2/download/dbupdate/monthly/dns | DNS Database Monthly |
| [**DbDnsWeekly**](DatabasesDNSApi.md#dbdnsweekly) | **GET** /v3.2/download/dbupdate/weekly/dns | DNS Database Weekly |

<a id="dbdnsdaily"></a>
# **DbDnsDaily**
> FileParameter DbDnsDaily (DateOnly? date = null)

DNS Database Daily

DNS Database Daily. Returns the file/snapshot described by this operation.

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
    public class DbDnsDailyExample
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
            var apiInstance = new DatabasesDNSApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // DNS Database Daily
                FileParameter result = apiInstance.DbDnsDaily(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesDNSApi.DbDnsDaily: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbDnsDailyWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // DNS Database Daily
    ApiResponse<FileParameter> response = apiInstance.DbDnsDailyWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesDNSApi.DbDnsDailyWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **DateOnly?** | yyyy-MM-dd; omit for latest | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | CSV |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="dbdnsmonthly"></a>
# **DbDnsMonthly**
> FileParameter DbDnsMonthly (DateOnly? date = null)

DNS Database Monthly

DNS Database Monthly. Returns the file/snapshot described by this operation.

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
    public class DbDnsMonthlyExample
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
            var apiInstance = new DatabasesDNSApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // DNS Database Monthly
                FileParameter result = apiInstance.DbDnsMonthly(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesDNSApi.DbDnsMonthly: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbDnsMonthlyWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // DNS Database Monthly
    ApiResponse<FileParameter> response = apiInstance.DbDnsMonthlyWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesDNSApi.DbDnsMonthlyWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **DateOnly?** | yyyy-MM-dd; omit for latest | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | CSV |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="dbdnsweekly"></a>
# **DbDnsWeekly**
> FileParameter DbDnsWeekly (DateOnly? date = null)

DNS Database Weekly

DNS Database Weekly. Returns the file/snapshot described by this operation.

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
    public class DbDnsWeeklyExample
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
            var apiInstance = new DatabasesDNSApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // DNS Database Weekly
                FileParameter result = apiInstance.DbDnsWeekly(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesDNSApi.DbDnsWeekly: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbDnsWeeklyWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // DNS Database Weekly
    ApiResponse<FileParameter> response = apiInstance.DbDnsWeeklyWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesDNSApi.DbDnsWeeklyWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **DateOnly?** | yyyy-MM-dd; omit for latest | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | CSV |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

