<h1 align="center"> ASP.NET Core </h1>
<br/><br/>

## 1. What server is used by ASP.NET Core. What are the maing characteristics of it?
### Answer
>ASP.NET Core uses Kestrel as its default web server. Kestrel is a lightweight, fast, and cross-platform HTTP server that is designed specifically for ASP.NET Core applications. It is highly optimized for performance and scalability, making it a great choice for high-traffic web applications.

>Some of the main characteristics of Kestrel are:
> * **Cross-platform:** Kestrel runs on Windows, macOS, and Linux, which makes it easy to develop and deploy ASP.NET Core applications on any operating system.
> * **Lightweight::** Kestrel is designed to be fast, efficient, and lightweight, which helps to reduce the memory footprint and CPU usage of ASP.NET Core applications.
> * **Scalable::** Kestrel is designed to be highly scalable, which makes it well-suited for high-traffic web applications.
> * **Secure::** Kestrel implements various security features, such as HTTPS and HTTP/2, which helps to secure ASP.NET Core applications and protect sensitive data.
> * **Extensible::** Kestrel provides a flexible architecture that makes it easy to add custom functionality, such as custom request handling, to an ASP.NET Core application.

>Kestrel has been designed and optimized specifically for ASP.NET Core, and it provides a number of features that are well-suited for production scenarios, including support for secure connections using SSL/TLS, the ability to handle large numbers of concurrent connections, and the ability to handle high-volume traffic.

>That being said, it is important to keep in mind that Kestrel is not a full-featured production server, and it may not have all of the features and capabilities of more established production servers, such as IIS or Nginx. As a result, it is typically recommended to use Kestrel in combination with a reverse proxy server in production environments. This allows you to take advantage of the performance and scalability of Kestrel, while also leveraging the advanced security and management features of the reverse proxy server.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 2. What is the role of the Startup class in ASP.NET Core, and how is it used to configure the application?
### Answer
>The Startup class in ASP.NET Core is an important part of an ASP.NET Core application and acts as the entry point for the application. It's where the configuration of the application takes place and where you configure services and middleware to be used by the application.

>The Startup class typically consists of two methods:

>`ConfigureServices` method: This method is used to configure the services that the application depends on. Services can be added to the dependency injection container using the IServiceCollection interface that is passed as a parameter to the method.

>`Configure` method: This method is used to configure the middleware components of the application. Middleware is executed in a pipeline, and the order of the components can be configured using this method.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 3. What is middleware 
### Answer
>In ASP.NET, middleware refers to software components that handle requests and responses between an application and the web server. These components can perform a variety of tasks such as authentication, routing, and caching. They are typically added to an application's pipeline using the built-in "Use" method, and they can be used to modify or extend the functionality of the application. Middleware components are often used to implement common functionality across multiple parts of an application, such as handling errors or logging data.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Right Answer                |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 4. What is the role of controllers in an ASP.NET Core MVC application, and how do they handle user requests?
### Answer
>Controllers in ASP.NET Core MVC are responsible for handling user requests and returning responses to the user. They define action methods that correspond to specific user actions, such as submitting a form or clicking a button. Controllers use model binding to extract data from incoming requests, and they use views to generate the HTML that is returned to the user.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 5. What is model binding in ASP.NET Core, and how is it used to map incoming request data to action method parameters?
### Answer
>Model binding in ASP.NET Core is a mechanism that maps the data from HTTP requests to action method parameters. This process makes it easier for developers to extract data from HTTP requests and use it in their application logic.
>By using model binding, you don't have to manually extract data from the request and manually create an instance of the model. This makes it easier to write clean and maintainable code, as well as reducing the chances of bugs and security issues.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 6. How does ASP.NET Core handle security, and what are some of the features and technologies that are used to secure applications?
### Answer
>ASP.NET Core provides a number of built-in security features and technologies to help you secure your applications. These include authentication and authorization, encryption and SSL, input validation and output encoding, and cross-site scripting (XSS) and cross-site request forgery (CSRF) protection. You can also add additional security features and technologies as needed, such as using OAuth or OpenID Connect for external authentication, or using anti-forgery tokens to protect against CSRF attacks.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 7. How does ASP.NET Core handle deployment and hosting, and what are some of the options for deploying and hosting ASP.NET Core applications?
### Answer
>ASP.NET Core is designed to be highly scalable and deployable, and it supports a variety of hosting options, including on-premises, cloud-based, and containers. You can deploy ASP.NET Core applications using various deployment technologies and services, including IIS, Kestrel, Docker, and Azure. Additionally, you can use continuous integration and delivery (CI/CD) tools and services, such as Visual Studio Team Services, to automate the deployment process.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 8. Please describe service lifetimes for dependency injection in ASP.NET Core  
### Answer
>In ASP.NET Core, dependency injection (DI) is used to manage the lifetime of services, which are objects that are created to perform a specific task or set of tasks. There are several different service lifetimes that can be used in ASP.NET Core, including:

>**Transient**: A new instance of the service is created each time it is requested. This lifetime is appropriate for services that do not maintain state or have a very short lifespan.

>**Scoped**: A new instance of the service is created for each request, but the same instance is used for all requests within the same scope. This lifetime is appropriate for services that maintain state and need to be created and disposed of on a per-request basis.

>**Singleton**: A single instance of the service is created and shared by all requests. This lifetime is appropriate for services that are long-lived and do not maintain state.

>**Instance**: An instance of the service is provided explicitly and the DI container will not dispose it. This lifetime is appropriate for service that you want to manage the lifetime, for example, when you want to dispose them when you are done using them.

>You can set the lifetime of a service by using the appropriate method of the `IServiceCollection` interface when adding the service to the DI container. For example, to add a service with a transient lifetime, you would use the AddTransient method:
```C#
services.AddTransient<MyService>();
```
You can also set the lifetime of a service using attributes, for example `[Transient]` or `[Scoped]`
```C#
[Transient]
public class MyService { }
```
>In summary, the service lifetimes in ASP.NET Core determine how long a service is kept in memory, and how many instances of the service are created. There are 4 types of service lifetimes: `Transient`, `Scoped`, `Singleton`, and `Instance`. You can set the lifetime of a service by using the appropriate method of the IServiceCollection interface when adding the service to the DI container, or by using attributes.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | Mentions Instance |
---
<br/><br/>

## 9. How does ASP.NET Core handle configuration, and what are some of the options for managing and storing configuration data for an ASP.NET Core application?
### Answer
>ASP.NET Core provides a number of options for managing and storing configuration data for your application. This includes support for `appsettings.json`, environment variables, command-line arguments, and custom configuration sources. You can also use the `IConfiguration` interface and the `ConfigurationBuilder` class to manage and retrieve configuration data from various sources in your application. Additionally, you can use `Azure Key Vault` or other cloud-based configuration stores to manage and store sensitive configuration data securely.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 10. What is HTTPS, SSL and TLS. How it works?
### Answer
>HTTPS (Hypertext Transfer Protocol Secure) is a widely used protocol for secure communication over the internet. It is built on top of SSL/TLS and provides secure communication for web browsing, email, and other internet services.

>When you access a website using HTTPS, your browser establishes a secure connection to the website's server using SSL/TLS. The SSL/TLS protocol provides encryption for the data that is transmitted between the browser and server, and it also verifies the identity of the server. This protects against eavesdropping, tampering, and other forms of tampering with the data being transmitted.

>In order to use HTTPS, a website must obtain an SSL/TLS certificate from a trusted certificate authority. The certificate contains information about the identity of the website, including its domain name, and is used to verify the identity of the website during the SSL/TLS handshake.

>Once the SSL/TLS connection is established, all communication between the browser and server is encrypted, and the data is transmitted over an HTTPS connection. This ensures that sensitive information, such as passwords and credit card numbers, is protected during transmission.

>In short, HTTPS is built on top of SSL/TLS and provides a secure communication channel for web browsing and other internet services. The use of SSL/TLS certificates and the encryption provided by SSL/TLS are critical components of HTTPS, and they ensure the privacy and security of sensitive information transmitted over the internet.

>### **Here is how it works**
>The client (typically a web browser) sends a request to access a website using HTTPS. <br />
>The server sends back its SSL/TLS certificate, which includes information about the identity of the website and is signed by a trusted certificate authority (CA). <br />
>The client verifies the identity of the server using the information in the certificate and checks that it has been signed by a trusted CA. If the certificate is invalid or cannot be verified, the connection will not be established. <br />
>The client and server then negotiate an encryption method to use for the session. They choose a common encryption algorithm and generate a unique session key to use for the encryption. <br />
>The client and server use the agreed-upon encryption method and the session key to establish an encrypted connection. All data transmitted between the client and server during the session is encrypted using the session key. <br />
>The client sends its request over the encrypted connection, and the server sends back the requested data in an encrypted format. <br />
>After the session is complete, the encrypted connection is closed. <br />

>### **SSL and TLS**
>
>SSL (Secure Sockets Layer) and TLS (Transport Layer Security) are cryptographic protocols that provide secure communication over the internet. They are used to secure sensitive information, such as credit card numbers and passwords, during transmission over the internet.

>SSL was originally developed by Netscape in the 1990s and was the first widely-used security protocol for the web. However, due to various security weaknesses and vulnerabilities that were discovered over time, SSL was replaced by TLS, which is now the most widely-used security protocol on the web.

>TLS is an updated version of SSL that provides stronger security and more flexible authentication options. It works by establishing an encrypted link between a client and a server, and then transmitting data over that link. The encryption is accomplished using public-key cryptography, and the specific encryption algorithms used are negotiated between the client and server at the start of the session.

>Both SSL and TLS are used to secure various types of internet communications, including web browsing, email, instant messaging, and voice-over-IP (VoIP) conversations. The use of SSL/TLS is essential for protecting sensitive information, and it is a critical component of online security.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>
