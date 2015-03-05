#开始使用Yeoman - 编写自己的generator

很多时候，你可能需要为自己的项目量身定做生成器，Yeoman提供了api供开发者编写自己的generator

##generator本质

generator本质上是`Node.js module`(以下用module表示)，所以当你创建generator时，事实上是创建一个`module`。

> 如果你不知道`module`，可以点[这里](http://nodejs.org/api/modules.html)

创建`module`：

1. 新建文件夹`generator-try-yeoman-demo`
2. 每个`module`都有个清单文件`package.json`，可通过`npm init`创建，有效的清单文件大致如下：

    ```
    {
      "name": "generator-name",
      "version": "0.1.0",
      "description": "",
      "keywords": ["yeoman-generator"],
      "dependencies": {
        "yeoman-generator": "^0.17.3"
      }
    }
    ```
3. 清单里的`name`必须是`generator-`开头，`keywords`里必须包含`yeoman-generator`，`description`必须定义
让[generators page](http://yeoman.io/generators)建立索引
4. 清单中的`dependencies`表示模块的依赖，可通过`npm install --save xxxx`来安装`xxxx`模块，其中的
`--save`参数表示安装完成后，会将依赖加到清单的`denpendencies`，所以上面显示的依赖，可通过执行：
    
    ```
    npm install --save yeoman-generator
    ```
    完成
5. 有关`package.json`的其他配置，可以点[这里](https://docs.npmjs.com/files/package.json)

##generator的结构

Yeoman会深度链接到generator的文件结构，每一个子生成器会有自己单独的一个文件夹

当你执行`yo name`时，会执行默认的`app`生成器，源文件必须是在`app/`的目录下

当你执行`yo name:subcommand`时，执行的是名为`subcommand`的子生成器，源文件在`subcommand/`目录下

有效的文件结构大致如下：

```
├───package.json
├───app/
│   └───index.js
└───router/
    └───index.js
```

上面的文件结构会暴露`yo name`和`yo name:router`两个命令

如果你不想把所有代码都直接放在生成器的根目录下，也可以将文件结构改成如下：

```
├───package.json
└───generators/
    ├───app/
    │   └───index.js
    └───router/
        └───index.js
```
