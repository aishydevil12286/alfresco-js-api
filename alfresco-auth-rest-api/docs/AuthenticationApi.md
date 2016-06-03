# AlfrescoAuthRestApi.AuthenticationApi

All URIs are relative to *https://localhost/alfresco/api/-default-/public/authentication/versions/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createTicket**](AuthenticationApi.md#createTicket) | **POST** /tickets | Create ticket (login)
[**deleteTicket**](AuthenticationApi.md#deleteTicket) | **DELETE** /tickets/-me- | Delete ticket (logout)
[**validateTicket**](AuthenticationApi.md#validateTicket) | **GET** /tickets/-me- | Validate ticket


<a name="createTicket"></a>
# **createTicket**
> LoginTicketEntry createTicket(loginRequest)

Create ticket (login)

Logs in and returns the new authentication ticket.\nThe userId and password properties are mandatory in the request body. For example:\n&#x60;&#x60;&#x60;JSON\n{\n    \&quot;userId\&quot;: \&quot;jbloggs\&quot;,\n    \&quot;password\&quot;: \&quot;password\&quot;\n}\n&#x60;&#x60;&#x60;\nTo use the ticket in future requests you should pass it in the request header.\nFor example using Javascript:\n  &#x60;&#x60;&#x60;Javascript\n    request.setRequestHeader (\&quot;Authorization\&quot;, \&quot;Basic \&quot; + btoa(ticket));\n  &#x60;&#x60;&#x60;\n

### Example
```javascript
var AlfrescoAuthRestApi = require('alfresco-auth-rest-api');
var defaultClient = AlfrescoAuthRestApi.ApiClient.default;

// Configure HTTP basic authorization: basicAuth
var basicAuth = defaultClient.authentications['basicAuth'];
basicAuth.username = 'YOUR USERNAME'
basicAuth.password = 'YOUR PASSWORD'

var apiInstance = new AlfrescoAuthRestApi.AuthenticationApi()

var loginRequest = new AlfrescoAuthRestApi.LoginRequest(); // {LoginRequest} The user credential.

apiInstance.createTicket(loginRequest).then(function(data) {
  console.log('API called successfully. Returned data: ' + data);
}, function(error) {
  console.error(error);
});

```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **loginRequest** | [**LoginRequest**](LoginRequest.md)| The user credential. | 

### Return type

[**LoginTicketEntry**](LoginTicketEntry.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

<a name="deleteTicket"></a>
# **deleteTicket**
> deleteTicket

Delete ticket (logout)

Deletes logged in ticket (logout).\n

### Example
```javascript
var AlfrescoAuthRestApi = require('alfresco-auth-rest-api');
var defaultClient = AlfrescoAuthRestApi.ApiClient.default;

// Configure HTTP basic authorization: basicAuth
var basicAuth = defaultClient.authentications['basicAuth'];
basicAuth.username = 'YOUR USERNAME'
basicAuth.password = 'YOUR PASSWORD'

var apiInstance = new AlfrescoAuthRestApi.AuthenticationApi()
apiInstance.deleteTicket().then(function() {
  console.log('API called successfully.');
}, function(error) {
  console.error(error);
});

```

### Parameters
This endpoint does not need any parameter.

### Return type

null (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

<a name="validateTicket"></a>
# **validateTicket**
> ValidateTicketEntry validateTicket

Validate ticket

Validates the specified ticket (derived from Authorization header) is still valid.\n\nFor example, you can pass the Authorization request header using Javascript:\n  &#x60;&#x60;&#x60;Javascript\n    request.setRequestHeader (\&quot;Authorization\&quot;, \&quot;Basic \&quot; + btoa(ticket));\n  &#x60;&#x60;&#x60;\n

### Example
```javascript
var AlfrescoAuthRestApi = require('alfresco-auth-rest-api');
var defaultClient = AlfrescoAuthRestApi.ApiClient.default;

// Configure HTTP basic authorization: basicAuth
var basicAuth = defaultClient.authentications['basicAuth'];
basicAuth.username = 'YOUR USERNAME'
basicAuth.password = 'YOUR PASSWORD'

var apiInstance = new AlfrescoAuthRestApi.AuthenticationApi()
apiInstance.validateTicket().then(function(data) {
  console.log('API called successfully. Returned data: ' + data);
}, function(error) {
  console.error(error);
});

```

### Parameters
This endpoint does not need any parameter.

### Return type

[**ValidateTicketEntry**](ValidateTicketEntry.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json
