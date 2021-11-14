# 端口探测

masscan   UDP 用这个扫  full 1-65535 but it has a high posibility to have false positive and false negative.

nmap   should try to scan common udp ports in my list

UDP 扫描总是不可靠，目前感觉最可靠的还是nmap手工指定端口进行UDP扫描

rustscan [https://github.com/RustScan/RustScan/](https://github.com/RustScan/RustScan/)   docker version not stable maybe try install directly

netcat   can UDP

ncat
