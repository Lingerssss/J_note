# 1. BinaryFormatter

### Reason:

Package "TableExporter" need turn on

### Solution:

Add

```c#
<EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
```

in .csproj file

### Log:

```bash
2022/09/15 12:01:02.092||Error||FileCabinetService||GET https://filecabsvc-qa.pwcias.local/archive-assignees/a371a010-f294-4176-afe3-af0900840514 System.NotSupportedException: BinaryFormatter serialization and deserialization are disabled within this application. See https://aka.ms/binaryformatter for more information.||System.NotSupportedException: BinaryFormatter serialization and deserialization are disabled within this application. See https://aka.ms/binaryformatter for more information.
   at System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize(Stream serializationStream, Object graph)
   at TableExporter.Services.TableExportService.DeepClone(Object original)
   at TableExporter.Services.TableExportService.<>c__DisplayClass6_0.<ConvertTableInfo>b__0(OrderedDictionary a)
   at System.Linq.Enumerable.SelectListIterator`2.ToList()
   at TableExporter.Services.TableExportService.ConvertTableInfo(String ids, ITableExportConfig tableExportConfig, Dictionary`2 allJsonDictionary, Dictionary`2 nonPiiJsonDictionary)
   at TableExporter.Services.TableExportService.GetTableInfo(String ids)
   at TableExporter.Services.TableExportService.ExportTableInfo(Guid[] ids)
   at FileCabinets.Service.Controllers.ArchiveAssigneeFileCabinetsController.Get(Guid assigneeId) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Controllers\ArchiveAssigneeFileCabinetsController.cs:line 45
   at lambda_method452(Closure , Object , Object[] )
   at Microsoft.AspNetCore.Mvc.Infrastructure.ActionMethodExecutor.SyncActionResultExecutor.Execute(IActionResultTypeMapper mapper, ObjectMethodExecutor executor, Object controller, Object[] arguments)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.<InvokeActionMethodAsync>g__Logged|12_1(ControllerActionInvoker invoker)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.<InvokeNextActionFilterAsync>g__Awaited|10_0(ControllerActionInvoker invoker, Task lastTask, State next, Scope scope, Object state, Boolean isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.Rethrow(ActionExecutedContextSealed context)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.Next(State& next, Scope& scope, Object& state, Boolean& isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.InvokeInnerFilterAsync()
--- End of stack trace from previous location ---
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.<InvokeNextExceptionFilterAsync>g__Awaited|26_0(ResourceInvoker invoker, Task lastTask, State next, Scope scope, Object state, Boolean isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.Rethrow(ExceptionContextSealed context)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.Next(State& next, Scope& scope, Object& state, Boolean& isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.InvokeFilterPipelineAsync()
--- End of stack trace from previous location ---
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.<InvokeAsync>g__Logged|17_1(ResourceInvoker invoker)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.<InvokeAsync>g__Logged|17_1(ResourceInvoker invoker)
   at Microsoft.AspNetCore.Routing.EndpointMiddleware.<Invoke>g__AwaitRequestTask|6_0(Endpoint endpoint, Task requestTask, ILogger logger)
   at FileCabinets.Service.Startup.<Configure>b__3_0(HttpContext context, Func`1 next) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Startup.cs:line
```



## 2. Value cannot be null

### Reson:

There are dirty data in qa enviroment

### Solution:

Clear the dirty data

### Log:

```
2022/09/15 08:31:08.124||Error||FileCabinetService||GET https://filecabsvc-qa.pwcias.local/assignees/76a1c4dc-17bf-4188-bfe9-a1f10085a6ed/filecabinets System.ArgumentNullException: Value cannot be null. (Parameter 'element')||System.ArgumentNullException: Value cannot be null. (Parameter 'element')
   at System.Attribute.GetCustomAttributes(MemberInfo element, Type attributeType, Boolean inherit)
   at System.Attribute.GetCustomAttribute(MemberInfo element, Type attributeType, Boolean inherit)
   at FileCabinets.Service.Extensions.EnumExtension.ToDescription(Enum value) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Extensions\EnumExtension.cs:line 50
   at FileCabinets.Service.Controllers.FileCabinetMapper.ToDto(FileCabinet fileCabinet, FileMetadata fileMetadata, Uri requestUri, IUrlHelper urlHelper, DownloadHistory[] downloadHistories, Message message) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Controllers\FileCabinetMapper.cs:line 14
   at FileCabinets.Service.Services.AssigneeFileCabinetService.<>c__DisplayClass10_0.<GetFileCabinetsDto>b__4(FileCabinet fileCabinet) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Services\AssigneeFileCabinetService.cs:line 56
   at System.Linq.Enumerable.SelectListIterator`2.ToList()
   at FileCabinets.Service.Services.AssigneeFileCabinetService.GetFileCabinetsDto(Guid assigneeId, Uri requestUri, IUrlHelper urlHelper) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Services\AssigneeFileCabinetService.cs:line 55
   at lambda_method377(Closure , Object , Object[] )
   at Microsoft.AspNetCore.Mvc.Infrastructure.ActionMethodExecutor.SyncObjectResultExecutor.Execute(IActionResultTypeMapper mapper, ObjectMethodExecutor executor, Object controller, Object[] arguments)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.<InvokeActionMethodAsync>g__Logged|12_1(ControllerActionInvoker invoker)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.<InvokeNextActionFilterAsync>g__Awaited|10_0(ControllerActionInvoker invoker, Task lastTask, State next, Scope scope, Object state, Boolean isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.Rethrow(ActionExecutedContextSealed context)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.Next(State& next, Scope& scope, Object& state, Boolean& isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker.InvokeInnerFilterAsync()
--- End of stack trace from previous location ---
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.<InvokeNextExceptionFilterAsync>g__Awaited|26_0(ResourceInvoker invoker, Task lastTask, State next, Scope scope, Object state, Boolean isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.Rethrow(ExceptionContextSealed context)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.Next(State& next, Scope& scope, Object& state, Boolean& isCompleted)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.InvokeFilterPipelineAsync()
--- End of stack trace from previous location ---
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.<InvokeAsync>g__Logged|17_1(ResourceInvoker invoker)
   at Microsoft.AspNetCore.Mvc.Infrastructure.ResourceInvoker.<InvokeAsync>g__Logged|17_1(ResourceInvoker invoker)
   at Microsoft.AspNetCore.Routing.EndpointMiddleware.<Invoke>g__AwaitRequestTask|6_0(Endpoint endpoint, Task requestTask, ILogger logger)
   at FileCabinets.Service.Startup.<Configure>b__3_0(HttpContext context, Func`1 next) in C:\ado_agent\_work\17\s\src\file-cabinet-service\Startup.cs:line 97
```





-- use [filecabinet-qa]

-- select * from filecabinet where AssigneeId = '76a1c4dc-17bf-4188-bfe9-a1f10085a6ed'