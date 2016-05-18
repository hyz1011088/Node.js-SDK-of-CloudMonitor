# How to use Node.js SDK of Aliyun CloudMonitor to get the detail monitored data


### Install Nodejs and update：

1.Install in centos 6.5 64bit:
```
yum -y install gcc make gcc-c++ openssl-devel wget
wget http://nodejs.org/dist/v0.10.26/node-v0.10.26.tar.gz
tar -zvxf node-v0.10.26.tar.gz
cd node-v0.10.26
make && make install
node -v
```
2.update
```
npm install -g n
n stable
node -v
```

### Install and update npm:
```
npm install npm -g
npm -v
```

### Install aliyun-metrics:
```
npm install aliyun-metrics
```

### Use SDK:
```
node 1.js
```
sample code :1.js
```
var Metrics = require("aliyun-metrics")

var client=new Metrics({
        accesskeyId: "---",
        accesskeySecret: "---"
})

client.queryData({
        project:"acs_ecs",
        metric:"vm.MemoryUtilization",
        period:60,
        startTime:"2016-05-16T12:20:00Z",
        endTime:"2016-05-16T13:00:00Z",
        dimensions:"{instanceId:'---'}"
}, function(error, data){
        if (error)
                console.log(error)
        else if (!data)
                console.log("data is null")
        else
                console.log(data)
});
```

### Reference:
[Node.js SDK](https://help.aliyun.com/document_detail/28623.html?spm=5176.doc28623.6.139.g7n42y)
[Install NodeJS](http://www.cnblogs.com/hamy/p/3632574.html)
[Update NodeJS](http://www.jb51.net/article/52409.htm)
[Install nodejs&npm](https://docs.npmjs.com/getting-started/installing-node?spm=5176.doc28623.2.1.g7n42y)
