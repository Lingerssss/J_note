```apl
[14:59:35 INF] Reading package info from nuspec C:\workspace\FileCabinet-Service\src\file-cabinet-service\file-cabinet-service.nuspec.
[14:59:35 ERR] An unsupported project type was detected. We do not support conversion of these projects.
[14:59:35 INF] No projects have been found to match your criteria.
```



Problem:

An unsupported project type was detected. We do not support conversion of these projects.



Reference Link:

[Unsupported Project · Issue #274 · hvanbakel/CsprojToVs2017 (github.com)](https://github.com/hvanbakel/CsprojToVs2017/issues/274)



Migrate-2019 doesn't support:

```c#
private static readonly Guid[] unsupportedGuids =
		{
			Guid.ParseExact("8BB2217D-0F2D-49D1-97BC-3654ED321F3B", "D"), // ASP.NET 5
			Guid.ParseExact("603C0E0B-DB56-11DC-BE95-000D561079B0", "D"), // ASP.NET MVC 1
			Guid.ParseExact("F85E285D-A4E0-4152-9332-AB1D724D3325", "D"), // ASP.NET MVC 2
			Guid.ParseExact("E53F8FEA-EAE0-44A6-8774-FFD645390401", "D"), // ASP.NET MVC 3
			Guid.ParseExact("E3E379DF-F4C6-4180-9B81-6769533ABE47", "D"), // ASP.NET MVC 4
			Guid.ParseExact("349C5851-65DF-11DA-9384-00065B846F21", "D"), // ASP.NET MVC 5
		};
```



Reason:

```xml
 <ProjectTypeGuids>{E3E379DF-F4C6-4180-9B81-6769533ABE47};{349c5851-65df-11da-9384-00065b846f21};
```



FileCabinets service is based on asp.net mvc 4/5



# FileCabinets service



### 1. Size: 

Soliton Contains 5 projects and 2 test projects



### 2. Risk:

Windows form

File-cabinet-encryption



### 3.Key problem



Remove: System.web



UrlHelper to IUrlHelper

.Route() method should be replaced with routeUrl







# Feature: FileCabinets service

# 

## Story:

1. ### file-cabinet-service (done) -3

2. ### Migrator, eventstore migrator (half done)： -1

   check pipeline artifacts

3. ### tests: 218 API test cases

   测试中途mock 需要修改

4. ### ci scripts, app insights -1



## Risk:

1. ### new update on master

   ### 

























