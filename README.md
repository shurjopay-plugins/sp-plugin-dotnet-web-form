![ShurjoPay](https://shurjopay.com.bd/dev/images/shurjoPay.png) .NET Web Form Package (plugin)
[![.Nuget](https://badge.fury.io/nu/ShurjopayPlugin.svg)](https://www.nuget.org/packages/ShurjopayPlugin)
![downloads](https://img.shields.io/nuget/dt/ShurjopayPlugin)
[![license](https://badgen.net/pypi/license/pip/)](LICENSE)

Official shurjoPay .net package (plugin) for merchants or service providers to connect with shurjoPay Payment Gateway v2.1 developed and maintained by shurjoMukhi Limited.

This plugin package can be used with .NET Web Form applications (e.g. .NET Web Form).

This plugin package makes it easy for you to integrate with shurjoPay v1.0.0 with just three method calls:

- GetTokenAsync()
- InitiatePaymentAsync()
- VerifyPaymentAsync()

Also reduces many of the things that you had to do manually

- Handles http request and errors
- JSON serialization and deserialization
- Authentication during checkout and verification of payments

## Audience

This document is intended for the developers and technical personnel of merchants and service providers who want to integrate the shurjoPay online payment gateway using .net Web Form framework.

## How to use this shurjoPay Plugin


 > Use `shurjoPay Plugin Folder` to install this plugin inside your project environment.

```
shurjopay Folder
```

> Add Shurjopay Configuration to your project's web.config file.

```
 <appSettings>
 <add key="SP_USERNAME" value="sp_sandbox" />
 <add key="SP_PASSWORD" value="pyyk97hu&amp;6u6" />
 <add key="SP_CALLBACK" value="https://www.sandbox.shurjopayment.com/response" />
 <add key="SP_ENDPOINT" value="https://sandbox.shurjopayment.com/api/" />
 <add key="SP_PREFIX" value="NOK" />
</appSettings>
```

>Sample Payment Request Object
```c#
  Amount = "100",
  OrderId ="1234gg456",
  DiscountAmount = "0",
  DiscPercent = "0"
  ClientIp = "127.0.0.1",
  CustomerName = "Md Wali Mosnad Ayshik",
  CustomerPhone = "01775503498",
  CustomerEmail = "ayshikmee01@gmail.com",
  CustomerAddress = "Dhaka Bangladesh",
  CustomerCity = "Dhaka",
  CustomerState = "Kuril",
  CustomerPostcode = "2100",
  Currency = "BDT",
  CustomerCountry = "Bangladesh",
  ShippingAddress = "N/A",         
  ShippingCity = "N/A",                
  ShippingCountry = "N/A",          
  ReceivedPersonName = "N/A",    
  ShippingPhoneNumber = "N/A",  
  Value1 = "N/A", - Any extra value that you need later                        
  Value2 = "N/A", - Any extra value that you need later                            
  Value3 = "N/A", - Any extra value that you need later                             
  Value4 = "N/A", - Any extra value that you need later                
```

> Make Payment Request
```c#
  // Create an instance of ShurjoPayPlugin
  var shurjoPay = new ShurjoPayPlugin();

  // Initiate payment
  var paymentResponse = await shurjoPay.InitiatePaymentAsync(paymentDetails);

  // Redirect to ShurjoPay checkout URL
  Response.Redirect(paymentResponse.CheckoutUrl);
```


> Payment verification can be done after each transaction with shurjopay order id.

```c#
 var shurjoPayPlugin = new ShurjoPayPlugin();
 var verificationResult = await shurjoPayPlugin.VerifyPaymentAsync(orderId);
```

#### That's all! Now you are ready to use the .net web form plugin to seamlessly integrate with shurjoPay to make your payment system easy and smooth.

## References
1. [.Net Web Form example application](https://github.com/shurjopay-plugins/sp-plugin-usage-examples/tree/main/dotnet-webForm-app-dotnet-plugin) showing usage of the .Net Web Form plugin.
2. [Sample applications and projects](https://github.com/shurjopay-plugins/sp-plugin-usage-examples) in many different languages and frameworks showing shurjopay integration.
3. [shurjoPay Postman site](https://documenter.getpostman.com/view/6335853/U16dS8ig) illustrating the request and response flow using the sandbox system.
4. [shurjopay Plugins](https://github.com/shurjopay-plugins) home page on github

## License
This code is under the [MIT open source License](LICENSE).
#### Please [contact](https://shurjopay.com.bd/#contacts) with shurjoPay team for more detail.
### Copyright ©️2022 [ShurjoMukhi Limited](https://shurjopay.com.bd/)
