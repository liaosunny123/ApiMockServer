# ApiMockServer
Filtering api with target endpoint and mock response according to yml. | 根据配置自动拦截特定终结点的Api，并返回构造后的模拟信息。
# Description  
ApiMockServer can run in `attach mode` or `proxy mode`.  
**Attached Mode**:ApiMockServer will generate special dll with yml provided by user and inject to special startup process, in order to filtering api request from the target and mock response.  
**Proxy Mode**:ApiMockServer will run as a proxy server with can edit the request through the proxy process.  
# Usage  
Attach mode using single yml(Output: be-injected.res.dll):  
```bash
./apimockserver --mode=attach demo.yml ./be-injected.dll
```

Attach mode using multiplied yml(Output: be-injected.res.dll):
```bash
./apimockserver --mode=attach demo.yml&&demo2.yml ./be-injected.dll
```

Proxy mode(Default run on the port 8900):  
The config should be put into dir Config:
Such as:
```bash
apimockserver
Config
---|demo.yml
---|demo2.yml
```
And run:
```bash
./apimockserver --mode=proxy
```
These are some optional parameter:
```bash
-port=8900: Run on 8900
-https=enable: Enable https
-host=127.0.0.1: Run on 127.0.0.1
-log=enable: Enable log output
-middleware: Use middleware.(Please put in the dir middleware)
```
