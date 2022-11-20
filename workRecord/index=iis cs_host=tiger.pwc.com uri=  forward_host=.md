index="iis" cs_host="tiger.pwc.com" "uri="  forward_host=|



 index="iis" cs_host="tiger.pwc.com" "uri=" | stats count by cs_host

.*cs_uri_query.*\n | .*cs_method.*\n | .*uri.*\n
"cs_uri_query.*\n |"cs_method.*\n |"uri.*\n























































œ{"preview":false,"offset":50984,"result":{"X_Forwarded_For":"155.201.38.20,+10.243.129.39:5031","_raw":"2022-02-01 22:39:45 10.246.68.4 GET /resource uri=https%3A%2F%2Ftigerapi-prod.pwcias.local%2Fsearch%2Fassignee%3Fquery%3DDe%2520Greef%2509Koen 443 Domenica+Avellan 10.246.68.244 HTTP/1.1 Mozilla/5.0+(Windows+NT+10.0;+Win64;+x64)+AppleWebKit/537.36+(KHTML,+like+Gecko)+Chrome/97.0.4692.99+Safari/537.36 https://tiger.pwc.com/ tiger.pwc.com 200 0 0 71 155.201.38.20,+10.243.129.39:5031","_time":"2022-02-01T22:39:45.000+0000","c_ip":"10.246.68.244","cs_Referer":"https://tiger.pwc.com/","cs_User_Agent":"Mozilla/5.0+(Windows+NT+10.0;+Win64;+x64)+AppleWebKit/537.36+(KHTML,+like+Gecko)+Chrome/97.0.4692.99+Safari/537.36","cs_host":"tiger.pwc.com","cs_method":"GET","cs_uri_query":"uri=https%3A%2F%2Ftigerapi-prod.pwcias.local%2Fsearch%2Fassignee%3Fquery%3DDe%2520Greef%2509Koen","cs_uri_stem":"/resource","cs_username":"Domenica+Avellan","cs_version":"HTTP/1.1","date":"2022-02-01","date_hour":"22","date_mday":"1","date_minute":"39","date_month":"february","date_second":"45","date_wday":"tuesday","date_year":"2022","date_zone":"0","forward_host":"tigerapi-prod.pwcias.local","host":"WEZTIGERWPWV001","index":"iis","linecount":"1","s_ip":"10.246.68.4","s_port":"443","sc_status":"200","sc_substatus":"0","sc_win32_status":"0","source":"C:\\inetpub\\logs\\LogFiles\\W3SVC27\\u_ex220201_x.log","sourcetype":"iis","splunk_server":"WEZTIGERWPWV017","time":"22:39:45","time_taken":"71","uri":"https%3A%2F%2Ftigerapi-prod.pwcias.local%2Fsearch%2Fassignee%3Fquery%3DDe%2520Greef%2509Koen 443 Domenica+Avellan 10.246.68.244 HTTP/1.1 Mozilla/5.0+(Windows+NT+10.0;+Win64;+x64)+AppleWebKit/537.36+(KHTML,+like+Gecko)+Chrome/97.0.4692.99+Safari/537.36 https://tiger.pwc.com/ tiger.pwc.com 200 0 0 71 155.201.38.20"}}

```
//1. select 
_raw().*?(?=443)

//2. replace
.*(?=get /)|.*(?=delete /)|.*(?=post)|.*(?=patch)|.*(?=put)

//3.decode

//4.replace the true id number with "{id}""
\d+

//5.delete unused parts
/reso.*//|\?.*|,uri.*\n

//6.special delete
^.*(?=put)|^.*(?=patch)  
id.*id id
```







