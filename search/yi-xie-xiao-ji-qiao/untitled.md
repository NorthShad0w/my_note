# XSS 技巧

避免因为网络延迟浏览器优化用户体验导致跨站的引用链接失败（采用异步加载脚本）

* Use asynchronous script loading, using `<script src="..." async>` or `element.appendChild()`,
* [Submit the script provider to Google for whitelisting](https://docs.google.com/forms/d/e/1FAIpQLSdMQ7PfoVMob5OTXSgodoG5V1eNC5CyQ_qo4skbN62RDSEPcg/viewform).

```
var script = document.createElement('script');  
script.src = "....";  
document.head.appendChild(script);
```

做探针爬虫xss的时候，要注意去掉logout之类的链接，去掉delete之类的链接，免得被抓
