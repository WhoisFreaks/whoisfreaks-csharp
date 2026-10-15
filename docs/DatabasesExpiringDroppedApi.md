# WhoisFreaks.Api.DatabasesExpiringDroppedApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DbDropped**](DatabasesExpiringDroppedApi.md#dbdropped) | **GET** /v3.1/download/domainer/dropped | Dropped Domains |
| [**DbDroppedBacklinks**](DatabasesExpiringDroppedApi.md#dbdroppedbacklinks) | **GET** /v3.3/download/domainer/dropped/backlinks | Dropped With Backlinks |
| [**DbDroppedJson**](DatabasesExpiringDroppedApi.md#dbdroppedjson) | **GET** /v3.1/domains/dropped | Dropped Domains (JSON) |
| [**DbExpired**](DatabasesExpiringDroppedApi.md#dbexpired) | **GET** /v3.1/download/domainer/expired | Expiring Domains |
| [**DbExpiredCleaned**](DatabasesExpiringDroppedApi.md#dbexpiredcleaned) | **GET** /v3.1/download/domainer/expired/cleaned | Expiring Cleaned WHOIS |

<a id="dbdropped"></a>
# **DbDropped**
> FileParameter DbDropped (bool whois, DateOnly? date = null)

Dropped Domains

Dropped Domains. Returns the file/snapshot described by this operation.

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
    public class DbDroppedExample
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
            var apiInstance = new DatabasesExpiringDroppedApi(httpClient, config, httpClientHandler);
            var whois = true;  // bool | 
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Dropped Domains
                FileParameter result = apiInstance.DbDropped(whois, date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbDropped: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbDroppedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Dropped Domains
    ApiResponse<FileParameter> response = apiInstance.DbDroppedWithHttpInfo(whois, date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbDroppedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **whois** | **bool** |  |  |
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

<a id="dbdroppedbacklinks"></a>
# **DbDroppedBacklinks**
> FileParameter DbDroppedBacklinks (bool? whois = null, DateOnly? date = null)

Dropped With Backlinks

Dropped With Backlinks. Returns the file/snapshot described by this operation.

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
    public class DbDroppedBacklinksExample
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
            var apiInstance = new DatabasesExpiringDroppedApi(httpClient, config, httpClientHandler);
            var whois = true;  // bool? |  (optional) 
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Dropped With Backlinks
                FileParameter result = apiInstance.DbDroppedBacklinks(whois, date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbDroppedBacklinks: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbDroppedBacklinksWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Dropped With Backlinks
    ApiResponse<FileParameter> response = apiInstance.DbDroppedBacklinksWithHttpInfo(whois, date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbDroppedBacklinksWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **whois** | **bool?** |  | [optional]  |
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

<a id="dbdroppedjson"></a>
# **DbDroppedJson**
> List&lt;string&gt; DbDroppedJson (DateOnly? date = null, string? tlds = null)

Dropped Domains (JSON)

Dropped Domains (JSON). Returns the file/snapshot described by this operation.

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
    public class DbDroppedJsonExample
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
            var apiInstance = new DatabasesExpiringDroppedApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 
            var tlds = "com,net";  // string? |  (optional) 

            try
            {
                // Dropped Domains (JSON)
                List<string> result = apiInstance.DbDroppedJson(date, tlds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbDroppedJson: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbDroppedJsonWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Dropped Domains (JSON)
    ApiResponse<List<string>> response = apiInstance.DbDroppedJsonWithHttpInfo(date, tlds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbDroppedJsonWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **DateOnly?** | yyyy-MM-dd; omit for latest | [optional]  |
| **tlds** | **string?** |  | [optional]  |

### Return type

**List<string>**

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | JSON array of domains |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="dbexpired"></a>
# **DbExpired**
> FileParameter DbExpired (bool whois, DateOnly? date = null)

Expiring Domains

Expiring Domains. Returns the file/snapshot described by this operation.

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
    public class DbExpiredExample
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
            var apiInstance = new DatabasesExpiringDroppedApi(httpClient, config, httpClientHandler);
            var whois = true;  // bool | 
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Expiring Domains
                FileParameter result = apiInstance.DbExpired(whois, date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbExpired: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbExpiredWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Expiring Domains
    ApiResponse<FileParameter> response = apiInstance.DbExpiredWithHttpInfo(whois, date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbExpiredWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **whois** | **bool** |  |  |
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

<a id="dbexpiredcleaned"></a>
# **DbExpiredCleaned**
> FileParameter DbExpiredCleaned (DateOnly? date = null)

Expiring Cleaned WHOIS

Expiring Cleaned WHOIS. Returns the file/snapshot described by this operation.

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
    public class DbExpiredCleanedExample
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
            var apiInstance = new DatabasesExpiringDroppedApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2026-10-01");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Expiring Cleaned WHOIS
                FileParameter result = apiInstance.DbExpiredCleaned(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbExpiredCleaned: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbExpiredCleanedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Expiring Cleaned WHOIS
    ApiResponse<FileParameter> response = apiInstance.DbExpiredCleanedWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesExpiringDroppedApi.DbExpiredCleanedWithHttpInfo: " + e.Message);
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

