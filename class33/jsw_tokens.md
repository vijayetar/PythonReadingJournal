## JSON Web Tokens
[Home](../README.md) 

[Reference](https://jwt.io/introduction/)  
[Debugger](https://jwt.io/#debugger-io)
[JWT in DjangoRESTFramework](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)  
[Video for JWT in DjangoRESTFramework](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)  

* JSON Web Token (JWT) is a compact, URL-safe means of representing claims to be transferred between two parties.  
* The claims in a JWT are encoded as a JSON object that is used as the payload of a JSON Web Signature (JWS) structure or as the plaintext of a JSON Web Encryption (JWE) structure, enabling the claims to be digitally signed or integrity protected with a Message Authentication Code (MAC) and/or encrypted.  

### Useful in :
1. __Authorization__: 
2. __Information Exchange__: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. 

### Structure: 

```
JWS tokens are made of header.payload.signature as xxxxx.yyyyy.zzzzz
```

1. __Header__   : Has two parts:  
    * contains the type of the token, which is JWT,    
    * and the signing algorithm being used, such as HMAC SHA256 or RSA.
    ```
    {
        "alg": "HS256",
        "typ": "JWT"
    }
    ```

2. __Payload__ : It contains the claims  
    * _registered_: set of predifined [claims](https://tools.ietf.org/html/rfc7519#section-4.1)  
    * _public_: defined at will. But to avoid collisions, they should be defined in the [registry](https://www.iana.org/assignments/jwt/jwt.xhtml)  
    * _private_: custom claims created to share information between parties that agree on using them and are neither registered or public claims. 
    ```
    {
      "sub": "1234567890",
      "name": "John Doe",
      "admin": true
    }
    ```

3. __Signature__ : To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.  


```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

## How it works in Authentication?
![image](https://cdn2.auth0.com/docs/media/articles/api-auth/client-credentials-grant.png)

1. The application or client requests authorization to the authorization server. This is performed through one of the different authorization flows. For example, a typical OpenID Connect compliant web application will go through the /oauth/authorize endpoint using the authorization code flow.  
2. When the authorization is granted, the authorization server returns an access token to the application.  
3. The application uses the access token to access a protected resource (like an API).  

