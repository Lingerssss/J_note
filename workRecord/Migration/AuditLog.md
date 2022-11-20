在qaSplunk中以compensation service为例

Resource = *compensation/audit.log 修复





1.抓包首先应该需要自己终端信任 Charles 的 CA 证书，
2.请求的时候，Charles 通过自己的 CA 签名了一个自己的公钥，发送给客户端，客户端会认为请求来自服务器。
3.抓包工具就作为中间人了，中间人可以获取https数据包，但无法解密。


