# WhoisFreaks.Api.IPReputationApi

All URIs are relative to *https://api.whoisfreaks.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkIpReputation**](IPReputationApi.md#bulkipreputation) | **POST** /v1.0/security | Bulk IP Reputation |
| [**IpReputation**](IPReputationApi.md#ipreputation) | **GET** /v1.0/security | IP Reputation Lookup |

<a id="bulkipreputation"></a>
# **BulkIpReputation**
> List&lt;IpReputationResponse&gt; BulkIpReputation (BulkGeolocationRequest bulkGeolocationRequest)

Bulk IP Reputation

Up to 100 IPs.

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
    public class BulkIpReputationExample
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
            var apiInstance = new IPReputationApi(httpClient, config, httpClientHandler);
            var bulkGeolocationRequest = new BulkGeolocationRequest(); // BulkGeolocationRequest | 

            try
            {
                // Bulk IP Reputation
                List<IpReputationResponse> result = apiInstance.BulkIpReputation(bulkGeolocationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling IPReputationApi.BulkIpReputation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkIpReputationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk IP Reputation
    ApiResponse<List<IpReputationResponse>> response = apiInstance.BulkIpReputationWithHttpInfo(bulkGeolocationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling IPReputationApi.BulkIpReputationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkGeolocationRequest** | [**BulkGeolocationRequest**](BulkGeolocationRequest.md) |  |  |

### Return type

[**List&lt;IpReputationResponse&gt;**](IpReputationResponse.md)

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

<a id="ipreputation"></a>
# **IpReputation**
> IpReputationResponse IpReputation (string ip)

IP Reputation Lookup

Threat intel for IP: VPN, proxy, Tor, bots. 1 credit.

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
    public class IpReputationExample
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
            var apiInstance = new IPReputationApi(httpClient, config, httpClientHandler);
            var ip = "8.8.8.8";  // string | 

            try
            {
                // IP Reputation Lookup
                IpReputationResponse result = apiInstance.IpReputation(ip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling IPReputationApi.IpReputation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the IpReputationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // IP Reputation Lookup
    ApiResponse<IpReputationResponse> response = apiInstance.IpReputationWithHttpInfo(ip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling IPReputationApi.IpReputationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **ip** | **string** |  |  |

### Return type

[**IpReputationResponse**](IpReputationResponse.md)

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

