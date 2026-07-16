# WhoisFreaks.Api.DatabasesNewlyRegisteredApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DbNewlyCctld**](DatabasesNewlyRegisteredApi.md#dbnewlycctld) | **GET** /v3.1/download/domainer/cctld | Newly Registered ccTLD (CSV) |
| [**DbNewlyCctldCleaned**](DatabasesNewlyRegisteredApi.md#dbnewlycctldcleaned) | **GET** /v3.1/download/domainer/cctld/cleaned | Newly Registered ccTLD Cleaned WHOIS (CSV) |
| [**DbNewlyCctldJson**](DatabasesNewlyRegisteredApi.md#dbnewlycctldjson) | **GET** /v3.1/domains/newly/cctld | Newly Registered ccTLD (JSON) |
| [**DbNewlyDns**](DatabasesNewlyRegisteredApi.md#dbnewlydns) | **GET** /v3.1/download/domainer/newly/dns | Newly Registered With DNS |
| [**DbNewlyGtld**](DatabasesNewlyRegisteredApi.md#dbnewlygtld) | **GET** /v3.1/download/domainer/gtld | Newly Registered gTLD (CSV) |
| [**DbNewlyGtldCleaned**](DatabasesNewlyRegisteredApi.md#dbnewlygtldcleaned) | **GET** /v3.1/download/domainer/gtld/cleaned | Newly Registered gTLD Cleaned WHOIS (CSV) |
| [**DbNewlyGtldJson**](DatabasesNewlyRegisteredApi.md#dbnewlygtldjson) | **GET** /v3.1/domains/newly/gtld | Newly Registered gTLD (JSON) |

<a id="dbnewlycctld"></a>
# **DbNewlyCctld**
> FileParameter DbNewlyCctld (bool whois, DateOnly? date = null, string? tlds = null)

Newly Registered ccTLD (CSV)

Newly Registered ccTLD (CSV). Returns the file/snapshot described by this operation.

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
    public class DbNewlyCctldExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var whois = true;  // bool | 
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 
            var tlds = "tlds_example";  // string? |  (optional) 

            try
            {
                // Newly Registered ccTLD (CSV)
                FileParameter result = apiInstance.DbNewlyCctld(whois, date, tlds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyCctld: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyCctldWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered ccTLD (CSV)
    ApiResponse<FileParameter> response = apiInstance.DbNewlyCctldWithHttpInfo(whois, date, tlds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyCctldWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **whois** | **bool** |  |  |
| **date** | **DateOnly?** | yyyy-MM-dd; omit for latest | [optional]  |
| **tlds** | **string?** |  | [optional]  |

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

<a id="dbnewlycctldcleaned"></a>
# **DbNewlyCctldCleaned**
> FileParameter DbNewlyCctldCleaned (DateOnly? date = null)

Newly Registered ccTLD Cleaned WHOIS (CSV)

Newly Registered ccTLD Cleaned WHOIS (CSV). Returns the file/snapshot described by this operation.

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
    public class DbNewlyCctldCleanedExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Newly Registered ccTLD Cleaned WHOIS (CSV)
                FileParameter result = apiInstance.DbNewlyCctldCleaned(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyCctldCleaned: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyCctldCleanedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered ccTLD Cleaned WHOIS (CSV)
    ApiResponse<FileParameter> response = apiInstance.DbNewlyCctldCleanedWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyCctldCleanedWithHttpInfo: " + e.Message);
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

<a id="dbnewlycctldjson"></a>
# **DbNewlyCctldJson**
> List&lt;string&gt; DbNewlyCctldJson (DateOnly? date = null, string? tlds = null)

Newly Registered ccTLD (JSON)

Newly Registered ccTLD (JSON). Returns the file/snapshot described by this operation.

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
    public class DbNewlyCctldJsonExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 
            var tlds = "tlds_example";  // string? |  (optional) 

            try
            {
                // Newly Registered ccTLD (JSON)
                List<string> result = apiInstance.DbNewlyCctldJson(date, tlds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyCctldJson: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyCctldJsonWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered ccTLD (JSON)
    ApiResponse<List<string>> response = apiInstance.DbNewlyCctldJsonWithHttpInfo(date, tlds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyCctldJsonWithHttpInfo: " + e.Message);
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

<a id="dbnewlydns"></a>
# **DbNewlyDns**
> FileParameter DbNewlyDns (DateOnly? date = null)

Newly Registered With DNS

Newly Registered With DNS. Returns the file/snapshot described by this operation.

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
    public class DbNewlyDnsExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Newly Registered With DNS
                FileParameter result = apiInstance.DbNewlyDns(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyDns: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyDnsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered With DNS
    ApiResponse<FileParameter> response = apiInstance.DbNewlyDnsWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyDnsWithHttpInfo: " + e.Message);
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
| **200** | JSON array of domains with DNS |  -  |
| **4XX** | Error response (4XX) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="dbnewlygtld"></a>
# **DbNewlyGtld**
> FileParameter DbNewlyGtld (bool whois, DateOnly? date = null, string? tlds = null)

Newly Registered gTLD (CSV)

Newly Registered gTLD (CSV). Returns the file/snapshot described by this operation.

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
    public class DbNewlyGtldExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var whois = true;  // bool | 
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 
            var tlds = "tlds_example";  // string? |  (optional) 

            try
            {
                // Newly Registered gTLD (CSV)
                FileParameter result = apiInstance.DbNewlyGtld(whois, date, tlds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyGtld: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyGtldWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered gTLD (CSV)
    ApiResponse<FileParameter> response = apiInstance.DbNewlyGtldWithHttpInfo(whois, date, tlds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyGtldWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **whois** | **bool** |  |  |
| **date** | **DateOnly?** | yyyy-MM-dd; omit for latest | [optional]  |
| **tlds** | **string?** |  | [optional]  |

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

<a id="dbnewlygtldcleaned"></a>
# **DbNewlyGtldCleaned**
> FileParameter DbNewlyGtldCleaned (DateOnly? date = null)

Newly Registered gTLD Cleaned WHOIS (CSV)

Newly Registered gTLD Cleaned WHOIS (CSV). Returns the file/snapshot described by this operation.

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
    public class DbNewlyGtldCleanedExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 

            try
            {
                // Newly Registered gTLD Cleaned WHOIS (CSV)
                FileParameter result = apiInstance.DbNewlyGtldCleaned(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyGtldCleaned: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyGtldCleanedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered gTLD Cleaned WHOIS (CSV)
    ApiResponse<FileParameter> response = apiInstance.DbNewlyGtldCleanedWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyGtldCleanedWithHttpInfo: " + e.Message);
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

<a id="dbnewlygtldjson"></a>
# **DbNewlyGtldJson**
> List&lt;string&gt; DbNewlyGtldJson (DateOnly? date = null, string? tlds = null)

Newly Registered gTLD (JSON)

Newly Registered gTLD (JSON). Returns the file/snapshot described by this operation.

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
    public class DbNewlyGtldJsonExample
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
            var apiInstance = new DatabasesNewlyRegisteredApi(httpClient, config, httpClientHandler);
            var date = DateOnly.Parse("2013-10-20");  // DateOnly? | yyyy-MM-dd; omit for latest (optional) 
            var tlds = "tlds_example";  // string? |  (optional) 

            try
            {
                // Newly Registered gTLD (JSON)
                List<string> result = apiInstance.DbNewlyGtldJson(date, tlds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyGtldJson: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DbNewlyGtldJsonWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Newly Registered gTLD (JSON)
    ApiResponse<List<string>> response = apiInstance.DbNewlyGtldJsonWithHttpInfo(date, tlds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesNewlyRegisteredApi.DbNewlyGtldJsonWithHttpInfo: " + e.Message);
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

