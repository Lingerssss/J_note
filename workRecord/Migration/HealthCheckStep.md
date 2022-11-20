1. 在ConfigureServices中注册

   ```c#
   builderServices.AddHealthChecks().AddSqlServer(AppSettings.Config.DBConnectionString);
   ```

   需要安装AspNetCore.HealthChecks.SqlServer的nuget包

2. 在Configure中绑定路由

   ```c#
   app.UseEndpoints(HealthCheck);
   ```

3. 实现HealthCheck

   ```c#
    private static void HealthCheck(IEndpointRouteBuilder endpoints)
       {
           endpoints.MapHealthChecks("/health", new HealthCheckOptions
           {
               AllowCachingResponses = false,
               ResultStatusCodes =
               {
                   [HealthStatus.Healthy] = StatusCodes.Status200OK,
                   [HealthStatus.Degraded] = StatusCodes.Status200OK,
                   [HealthStatus.Unhealthy] = StatusCodes.Status503ServiceUnavailable
               },
               ResponseWriter = WriteResponse
           });
           endpoints.MapControllers();
    }
   ```

   

