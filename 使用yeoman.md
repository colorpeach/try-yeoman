#开始使用Yeoman - 使用Yeoman

[官方教程](http://yeoman.io/learning/index.html)

##找到对应的生成器（generator）

官网的教程里边推荐了`generator-webapp`，这个生成器会生成工程目录，其中包括：
[HTML5 Boilerplate](https://html5boilerplate.com/),
[jQuery](http://jquery.com/), 
[Modernizr](http://modernizr.com/), 
and [Bootstrap](http://twbs.github.io/bootstrap)，
同时还会生成`grunt`的配置文件`Gruntfile.js`，`bower`的配置文件`bower.json`


可以通过以下几种方式找到适合自己的生成器
* 在命令行中输入`yo`，然后选择`Install a generator`，可以搜索
* 进入官网的[Discovering generators](http://yeoman.io/generators/)
* 进入[npm](http://www.npmjs.org/)，搜索`yeoman generator`

##开始使用
首先，需要为新应用创建目录（文件夹），例如：

>  如果你想将工程放在`D`盘下，可以在`D`盘打开命令行工具（win7是`shift+鼠标右键`，选择'在此处打开命令行窗口'），
>   然后执行以下命令：  
>   ```
>  mkdir try-yeoman  //新建文件夹try-yeoman
>  cd try-yeoman     //将命令行执行路径设置为刚新建的文件夹
>  ```

然后，在找到了需要的generator之后，通过命令行安装，这里我们安装的是基于Angularjs工程的生成器

```
npm install -g generator-angular
```

现在，可以通过Yeoman快速搭建工程框架了：

```
yo angular
```

执行上面的命令后，会发现在刚才新建的`try-yeoman`目录下，生成了很多的目录和文件，
其中有`bower.json`和`Gruntfile.js`，这两个分别是工程的前端依赖（框架，控件等）和自动化构建工具grunt的配置文件，

通过命令

```
npm install     // 安装`package.json`里描述的依赖
bower install   // 安装`bower.json`里描述的依赖
```

安装工程的所有依赖

在安装完整个工程的依赖之后，便可以开始开发工作了。

通过`grunt serve`，可以在浏览器中预览刚刚生成的工程，并且在你修改代码后，浏览器会自动刷新。

除了上述所说的`yo angular`可以直接生成整个工程目录外，更多的开发工作中，你或许需要快速生成一些文件或目录，
Yeoman提供了`sub-generators`，上面的`generator-angular`就提供了一些：

```
 yo angular:controller myController     // 生成一个名字为myController的控制器文件
 yo angular:directive myDirective       // 生成一个名字为myDirective的指令文件
 yo angular:filter myFilter             // 生成一个名字为myFilter的Filter文件  
 yo angular:service myService           // 生成一个名字为myService的服务文件
```

更多`generator-angular`的`sub-generators`可以点击[这里](https://www.npmjs.com/package/generator-angular)

##工作流

使用Yeoman快速搭建好工程的后，使用[grunt](http://gruntjs.com/)和[bower](http://bower.io/)让工作更加高效




