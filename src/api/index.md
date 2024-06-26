---
outline: deep
---

# 第三方Api 文档


### <code>*axios*</code> 使用方法
1. 下载文件
```js
var path = '';
var url = '';
var writer = fs.createWriteStream(path);
axios.get(url,{responseType: 'stream'}).then(res=>{
    res.data.pipe(writer);
})
writer.on('finish',()=>{
    console.log('download success');
    writer.end();
});
```
2. 上传文件
```js
const FormData = require('form-data');
var filePath = '';
var url = '';
const formData = new FormData();
formData.append('file', fs.createReadStream(filePath), {
    filename: fileName,
});
const res = await axios.post(url,formData,{headers: {...formData.getHeaders()}});
console.log(res.data);
```

3. 接口超时
```js
const url = '';
axios.get(url,{timeout: 1000}).then(res=>{
    console.log(res.data);
}).catch(err=>{
    console.log(err);
    console.log('timeout');
});
```


### <code>*compress*</code> 用法
1. 压缩文件
```js
const compress = require('compress');
compressing.zip.compressFile(path.join(filePath, fileName), zipFilePath, { zipFileNameEncoding: 'UTF-8' })
      .then(() => {
        console.log('zip success');
      }).catch(err => {
        console.log(err);
      })
compressing.zip.compressDir(filePath, zipPath, { zipFileNameEncoding: 'UTF-8' })
      .then(() => {
        console.log('zip success');
      }).catch(err => {
        console.log(err);
      })

```
2. 解压文件
```js
const compress = require('compress');
compressing.zip.uncompress(path.join(filePath, fileName), unZipFilePath, { zipFileNameEncoding: 'UTF-8' })
      .then(() => {
        console.log('unzip success');
      }).catch(err => {
        console.log(err);
      })
```

### <code>*is-online*</code> 用法
```js
isOnline().then(online => {
  console.log(online ? 'Online' : 'Offline');
}).catch(err => {
  console.error(err);
});
```

### <code>*jquery*</code> 用法

1. 获取同级元素
```js
$('.class').siblings();//所有
$('.class').prev();//前
$('.class').after();//后

```

2. 遍历
```js
var obj = $(".class")
$.each(obj,function(index,item){
  console.log(index,item);
})

```
