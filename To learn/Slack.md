# 1.文档好乱

https://api.slack.com/authentication/basics





获取一个channel的历史对话，jiaxiTest的xoxb是xoxb-3562555357635-3548012861815-57B5FujXIrHALIrDyrSbYVsz<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220526022213765.png" alt="image-20220526022213765" style="zoom:50%;" />







```bash
curl https://slack.com/api/conversations.list -H "Authorization: Bearer xoxb-3562555357635-3548012861815-57B5FujXIrHALIrDyrSbYVsz"
```



```
curl -X POST -F channel=jiaxi -F text="Reminder" https://slack.com/api/chat.postMessage -H "Authorization: Bearer xoxb-3562555357635-3548012861815-57B5FujXIrHALIrDyrSbYVsz"
```



**Bot User OAuth Token**:

xoxb-3562555357635-3548012861815-57B5FujXIrHALIrDyrSbYVsz

```bash
export SLACK_BOT_TOKEN=xoxb-3562555357635-3548012861815-57B5FujXIrHALIrDyrSbYVsz
```

## App Credentials

**Signing Secret**：

dc9a09592777bc19ba14f6a21a4cc9f0

```bash
export SLACK_SIGNING_SECRET=dc9a09592777bc19ba14f6a21a4cc9f0
```