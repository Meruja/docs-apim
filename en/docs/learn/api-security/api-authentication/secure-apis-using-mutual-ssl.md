# Securing APIs with Mutual SSL

In contrast to the usual one-way SSL authentication where a client verifies the identity of the server, in mutual SSL the server validates the identity of the client so that both parties trust each other. This builds a system that has very tight security and avoids any requests made to the client to provide the username/password, as long as the server is aware of the certificates that belong to the client.

This section explains as to how APIs in WSO2 API Manager can be secured using mutual SSL in addition to OAuth2.

## Create an API Secured with Mutual SSL

1.  [Create an API]({{base_path}}/learn/design-api/create-api/create-a-rest-api).
2.  Click **Runtime Configurations**.
3.  Select **Mutual SSL**.
    [![]({{base_path}}/assets/img/learn/enable-mutual-ssl.png)]({{base_path}}/assets/img/learn/enable-mutual-ssl.png)

4.  Click **Add Certificate** to upload a new client certificate.
    
    !!! note
        This feature currently supports only the `.crt` format for certificates.

        If you need to use a certificate in any other format, you can convert it using a standard tool before uploading it.


5.  Provide an alias and public certificate. Select the tier that should be used to throttle out the calls using this particular client certificate and click **Upload**.
    [![]({{base_path}}/assets/img/learn/upload-certificate.png)]({{base_path}}/assets/img/learn/upload-certificate.png)
    
6.  **Save** the API
    
### Invoke an API secured with Mutual SSL using Postman

1.  Import the certificate and private key to Postman. Navigate to the certificates tab in Postman settings.
    
    [![]({{base_path}}/assets/img/learn/add-certificate-to-postman.png)]({{base_path}}/assets/img/learn/add-certificate-to-postman.png)
    
    Add the certificate and private key.
    [![]({{base_path}}/assets/img/learn/provide-crt-and-private-key.png)]({{base_path}}/assets/img/learn/provide-crt-and-private-key.png)
    
2.  Invoke the API from Postman.

### Limitations

Listed below are the known limitations for this feature.

-   Application subscription is not permitted for APIs that are only protected with Mutual SSL. Therefore, subscription/application-level throttling is not applicable to these types of APIs.

-   Resource-level throttling is not applicable to the APIs that are only protected with Mutual SSL.

-   Resource-level security will not be applicable to the APIs that are only protected with Mutual SSL.

-   Scope-level security will not be applicable to the APIs that are only protected with Mutual SSL.
