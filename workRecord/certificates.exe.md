Certutil.exe 

wif

生成新证书

New-SelfSignedCertificate -DnsName "localhost" -CertStoreLocation "cert:\LocalMachine\My" -Subject "CN=STSTestCert" -KeySpec KeyExchange -NotAfter (Get-Date).AddMonths(1200)






