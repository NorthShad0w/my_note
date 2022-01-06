# 出口网关ip

## linux

curl cip.cc   国内 带地址

curl www.cip.cc/208.67.200.21 特定ip

curl ifconfig.me  国外 纯ip  ifconfig.me/ua   useragent

curl ipinfo.io  国外 带地址

curl ipinfo.io/118.67.200.21 特定ip

## windows

ftp cip.cc

nslookup.exe myip.opendns.com resolver1.opendns.com

(iwr/Invoke-webrequest/curl/wget ipinfo.io).content

irm/invoke-restmethod ipinfo.io

(new-object System.net.webclient).downloadString("http://ipinfo.io/")

