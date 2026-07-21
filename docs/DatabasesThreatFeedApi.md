# WhoisFreaks.Api.DatabasesThreatFeedApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DownloadThreatFeedMalware**](DatabasesThreatFeedApi.md#downloadthreatfeedmalware) | **GET** /v3.4/download/threat-feed/malware | Download the daily malware threat feed (CSV) |
| [**DownloadThreatFeedMalwareSample**](DatabasesThreatFeedApi.md#downloadthreatfeedmalwaresample) | **GET** /v3.4/download/threat-feed/malware/sample | Download a sample of the malware threat feed (CSV) |
| [**DownloadThreatFeedPhishing**](DatabasesThreatFeedApi.md#downloadthreatfeedphishing) | **GET** /v3.4/download/threat-feed/phishing | Download the daily phishing threat feed (CSV) |
| [**DownloadThreatFeedPhishingSample**](DatabasesThreatFeedApi.md#downloadthreatfeedphishingsample) | **GET** /v3.4/download/threat-feed/phishing/sample | Download a sample of the phishing threat feed (CSV) |
| [**DownloadThreatFeedSpam**](DatabasesThreatFeedApi.md#downloadthreatfeedspam) | **GET** /v3.4/download/threat-feed/spam | Download the daily spam threat feed (CSV) |
| [**DownloadThreatFeedSpamSample**](DatabasesThreatFeedApi.md#downloadthreatfeedspamsample) | **GET** /v3.4/download/threat-feed/spam/sample | Download a sample of the spam threat feed (CSV) |

<a id="downloadthreatfeedmalware"></a>
# **DownloadThreatFeedMalware**
> FileParameter DownloadThreatFeedMalware (string? date = null)

Download the daily malware threat feed (CSV)

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
    public class DownloadThreatFeedMalwareExample
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
            var apiInstance = new DatabasesThreatFeedApi(httpClient, config, httpClientHandler);
            var date = "date_example";  // string? | Feed date (yyyy-MM-dd); defaults to latest available (optional) 

            try
            {
                // Download the daily malware threat feed (CSV)
                FileParameter result = apiInstance.DownloadThreatFeedMalware(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedMalware: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadThreatFeedMalwareWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download the daily malware threat feed (CSV)
    ApiResponse<FileParameter> response = apiInstance.DownloadThreatFeedMalwareWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedMalwareWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **string?** | Feed date (yyyy-MM-dd); defaults to latest available | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Malware threat feed as CSV (domain,threat_type,confidence,first_seen,last_seen,No_of_threat_matched_pivots) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadthreatfeedmalwaresample"></a>
# **DownloadThreatFeedMalwareSample**
> FileParameter DownloadThreatFeedMalwareSample ()

Download a sample of the malware threat feed (CSV)

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
    public class DownloadThreatFeedMalwareSampleExample
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
            var apiInstance = new DatabasesThreatFeedApi(httpClient, config, httpClientHandler);

            try
            {
                // Download a sample of the malware threat feed (CSV)
                FileParameter result = apiInstance.DownloadThreatFeedMalwareSample();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedMalwareSample: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadThreatFeedMalwareSampleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download a sample of the malware threat feed (CSV)
    ApiResponse<FileParameter> response = apiInstance.DownloadThreatFeedMalwareSampleWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedMalwareSampleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sample malware threat feed as CSV |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadthreatfeedphishing"></a>
# **DownloadThreatFeedPhishing**
> FileParameter DownloadThreatFeedPhishing (string? date = null)

Download the daily phishing threat feed (CSV)

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
    public class DownloadThreatFeedPhishingExample
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
            var apiInstance = new DatabasesThreatFeedApi(httpClient, config, httpClientHandler);
            var date = "date_example";  // string? | Feed date (yyyy-MM-dd); defaults to latest available (optional) 

            try
            {
                // Download the daily phishing threat feed (CSV)
                FileParameter result = apiInstance.DownloadThreatFeedPhishing(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedPhishing: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadThreatFeedPhishingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download the daily phishing threat feed (CSV)
    ApiResponse<FileParameter> response = apiInstance.DownloadThreatFeedPhishingWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedPhishingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **string?** | Feed date (yyyy-MM-dd); defaults to latest available | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phishing threat feed as CSV (domain,threat_type,confidence,first_seen,last_seen,No_of_threat_matched_pivots) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadthreatfeedphishingsample"></a>
# **DownloadThreatFeedPhishingSample**
> FileParameter DownloadThreatFeedPhishingSample ()

Download a sample of the phishing threat feed (CSV)

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
    public class DownloadThreatFeedPhishingSampleExample
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
            var apiInstance = new DatabasesThreatFeedApi(httpClient, config, httpClientHandler);

            try
            {
                // Download a sample of the phishing threat feed (CSV)
                FileParameter result = apiInstance.DownloadThreatFeedPhishingSample();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedPhishingSample: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadThreatFeedPhishingSampleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download a sample of the phishing threat feed (CSV)
    ApiResponse<FileParameter> response = apiInstance.DownloadThreatFeedPhishingSampleWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedPhishingSampleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sample phishing threat feed as CSV |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadthreatfeedspam"></a>
# **DownloadThreatFeedSpam**
> FileParameter DownloadThreatFeedSpam (string? date = null)

Download the daily spam threat feed (CSV)

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
    public class DownloadThreatFeedSpamExample
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
            var apiInstance = new DatabasesThreatFeedApi(httpClient, config, httpClientHandler);
            var date = "date_example";  // string? | Feed date (yyyy-MM-dd); defaults to latest available (optional) 

            try
            {
                // Download the daily spam threat feed (CSV)
                FileParameter result = apiInstance.DownloadThreatFeedSpam(date);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedSpam: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadThreatFeedSpamWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download the daily spam threat feed (CSV)
    ApiResponse<FileParameter> response = apiInstance.DownloadThreatFeedSpamWithHttpInfo(date);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedSpamWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **date** | **string?** | Feed date (yyyy-MM-dd); defaults to latest available | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Spam threat feed as CSV (domain,threat_type,confidence,first_seen,last_seen,No_of_threat_matched_pivots) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadthreatfeedspamsample"></a>
# **DownloadThreatFeedSpamSample**
> FileParameter DownloadThreatFeedSpamSample ()

Download a sample of the spam threat feed (CSV)

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
    public class DownloadThreatFeedSpamSampleExample
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
            var apiInstance = new DatabasesThreatFeedApi(httpClient, config, httpClientHandler);

            try
            {
                // Download a sample of the spam threat feed (CSV)
                FileParameter result = apiInstance.DownloadThreatFeedSpamSample();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedSpamSample: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadThreatFeedSpamSampleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download a sample of the spam threat feed (CSV)
    ApiResponse<FileParameter> response = apiInstance.DownloadThreatFeedSpamSampleWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling DatabasesThreatFeedApi.DownloadThreatFeedSpamSampleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sample spam threat feed as CSV |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

