```java
install feature[C:\workspace\AccountServices\tmp\working\IASAccountService.1.0.0\tools\deploy-website\health-check.ns.ps1] ends
Website [iasaccount-local] is ready.
install feature[C:\workspace\AccountServices\tmp\working\IASAccountService.1.0.0\tools\deploy-website\health-check.ns.ps1] ends
Source Package [ IASAccountService : 1.0.0 ]
Target HealthCheckUrl: [http://localhost:10110/health?check=all]
>>>>>>>>>>>>>>>>> Step Get content from url[http://localhost:10110/health?check=all] started...
Error and retry: Exception calling "DownloadString" with "1" argument(s): "The remote server returned an error: (500) Internal Server Error."
>>>>>>>>>>>>>>>>> Step Get content from url[http://localhost:10110/health?check=all] started...
Error and retry: Exception calling "DownloadString" with "1" argument(s): "The remote server returned an error: (500) Internal Server Error."
>>>>>>>>>>>>>>>>> Step Get content from url[http://localhost:10110/health?check=all] started...
Error and retry: Exception calling "DownloadString" with "1" argument(s): "The remote server returned an error: (500) Internal Server Error."
>>>>>>>>>>>>>>>>> Step Get content from url[http://localhost:10110/health?check=all] started...
Error: 2022-04-26 15:22:54:
At C:\workspace\AccountServices\tmp\working\IASAccountService.1.0.0\tools\deploy-website\website.fn.ns.ps1:7 char:13 +             (New-Object System.Net.WebClient).DownloadString($url) +             ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ [<<==>>] Exception: Exception calling "DownloadString" with "1" argument(s): "The remote server returned an error: (500) Internal Server Error." --> The remote server returned an error: (500) Internal Server Error.


```

AccountService - /src/account-service

iasaccountService- /src/account-web







MyPwCPinCodeControllerFacts.cs(51, 41): [CS1061] 'string' does not contain a definition for 'Matches' and no accessible extension method 'Matches' accepting a first argument of type 'string' could be found (are you missing a using directive or an assembly reference?)









MyPwCPinCodeControllerFacts.cs(51, 41): [CS1061] 'string' does not contain a definition for 'Matches' and no accessible extension method 'Matches' accepting a first argument of type 'string' could be found (are you missing a using directive or an assembly reference?)

