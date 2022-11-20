# Background

### Job Manager

Job Manager provides async queue service for other services.

 There are 2 parts of the Job Manager

- Job Dispatcher - website, and it provide 3 API, other service use the API to enqueue jobs 

- Job Worker -service, handle the enqueued jobs

The indication of a successful migration is the same working functionality as before migration, after deploying to further environment.



![job Manager](../../../../../Desktop/study/job Manager.png)



### IAS Canlendar

IAS Calendar service is one of the microservices that need to be migrated to NET6 under the scope of dotnet migration. 

![IAScalendar](../../../../../Library/Application Support/typora-user-images/Screen Shot 2022-07-19 at 15.44.04.png)