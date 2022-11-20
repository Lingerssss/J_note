修改model中映射的关系

1. 以修改DeviceTrialHistory为例，在这个类下新建一个类，类名DeviceTrialHistory+Map，

   如果原类直接继承于ActiveRecordBase，则Map无需像下面code中继承BelongsToPlatformUserMap。

   这是yangbei用于处理的一种方式。

   codeSample1;

   ```c#
   //code sample 1    
   public class DeviceTrialHistoryMap : BelongsToPlatformUserMap<DeviceTrialHistory>
       {
           public DeviceTrialHistoryMap() : base("DeviceTrialHistory")
           {
               Id(e => e.Id).GeneratedBy.GuidComb();
               Map(e => e.DeviceId).Column("DeviceId");
               Map(e => e.VisitTime).Column("VisitTime");
               Map(e => e.IsLocked).Column("IsLocked");
               Map(e => e.Type).Column("Type");
               Map(e => e.Username).Column("Username");
           }
       };
   ```

   

2. 删除Property这个attribute，在codesample1中添加Map

   ```c#
   [Property(Column = "DeviceId")]
           public string DeviceId { get; set; }
   ```

   

3. 完成所有字段的map后，将所有static方法迁移到DeviceTrialHistory+Service文件下



Guid.Comb()会生成顺序的guid