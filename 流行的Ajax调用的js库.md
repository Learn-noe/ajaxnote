## 1. Fetch ApI 
### 他是XMLHttpRequest的现代替代方法，用于从服务器检索资源。与XMLHttpRequest不同，他更加强大和具有意义。它提取遵循一个请求-响应方法，fetch提出请求并返回一个解析为ResPonse对象的Promise
#### 1> 可以传递一个Request对象来获取，或者，也可以获取资源的Url下面简单的实例：
####    fetch('http://www.example.com',{
####           method:'get'
####       })
####       .then(reponse=>response.json())
####      .then(jsonData=>console.log(jsonData)
####        .catch(err=>{console.log(error))}fetch的then方法返回一个响应对象，可以使用一系列的then进一步操作，
####        如果需要post表单或者使用Fetch创建AJAX文件上传，除了Fetch之外，您还需要一个输入表单，并使用FormData库来存储表单对象
####   2> var input=document.querySelector('input[type="file"]')
####       var data=new FormData()
####       data.append('file',input.files[0])
####        data.append('user','blizzerand')
####      fetch('/avatars',{
            method:'post',body:data
        })
##  2. Axios Axios是一个基于XMLHttpRequest构建的Js库 ，用于Ajax调用。它允许从浏览器和服务器发出HTTP请求。此外，它还支持ES6原生的Promise API aXIOS 的其他突出特点包括：
### 1> 拦截请求和响应
###    2> 使用promise来转换请求和响应数据。
###   3>自动转换JSON数据
###    4>取消实时请求
####        axios实例：
####       axios.get('/user?ID=12345')
####        .then(function(reaponse){
####            console.log(response);
####        })
####        .catch(function(error){
####            console.log(error);
####        });与Fetch相比，axios更加简单。让我们可以做一些复杂的事情，比如之前建立的Ajax上传器
####         var data=new FromData();
####        data.append('foo','bar');
####        data.append('file',document.getElementById('file'.files[0]));
####         var congig={
             onUpload:function(progressEvent){
                 var percentComleted=Math,round((progressEvent.load*100)/progressEvent.total);
             }
         };
         axios.put('upload/server',data,config)
         .then(function(res){
             output.className='container';
             output.innerHTML=res.data;
         })
         .catch(function(err){
             output.className='container text-danger';
             output.innerHTML=err.message;
         })Axios更具可读性。axios也受到了 React和vue等流行框架的欢迎。
##  3. Jquery
####       $.ajax({
####           url:'/users',
####           type:'get',
####            dataType:'json',
####           success:function(data){
####                console.log(data);
####            }
####            fail:function(){
####                console.log('Encountered an error')
####            }
####        });
####        ajax和FromDta上传的实例：
 ####       var fromData=new FromData();
####        fromData.append('file',$('#file')[0].file[0]);
####        $.ajax({
####           url:'upload.php',
####            type:'post',
####           data:fromData,
####            contentType:false,
####            processData:false,
####            success:function(data){
####                console.log(data);
####               alert(data);
####            }
####        });
## 4.SuperAgent 他是一个轻量级和渐进式AJAX库，更侧重与可读性和灵活性。SuperAgent还拥有一个温和的学习路线，不像其他Js库，他有一个相同的API Node.js模块。SuperAgent有一个请求对象，他接受GET,post,put,delete和head等方法然后可以调用.then,.end或新的await方法来处理响应，实例如下：
####        request
####            .post('/api/pet')
####            .send({name:'Manny',species:'cat'})
####            .set('X-API-key','foobar')
####            .set('Accept','application/json')
####            .then(function(res){
####                alert('bar' + JSON.stringify(res.body));
####            });
####            如果上传一个ajax库文件
####           request
####                .post('/upload')
####                .filed('user[name]','Tobi')
####                .filed('user[email]','tobi@learnboost.com')
####                .filed('friends[]',['loki','jane'])
####                .attach('image','path/to/tobi.png')
####                .then(callback)

## 5. Request-简化的HTTP客户端
### Request是进行HTTP调用的最简单的方法之一。结构和语法与在node.js中处理请求的方式非常相似，值得一提的是：Request是可用的HTTP库之一。实例如下：
####           var request=require('request');
####            request('http://www.google.com',function(error,responsebody){
####                console.log('error':err);
####                console.log('statusCode',reaponse &&response.statusCode);
####                console.log('body:',body);
####            }),