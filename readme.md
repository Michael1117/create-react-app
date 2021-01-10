## 1. monorepo管理

- monorepo是项目代码的一个方式，指在一个项目仓库(repo)中管理多个模块/包(package)
- monorepo最主要的好处是统一的工作流和代码共享
- Lerna是一个管理多个npm模块的工具，优化维护多包的工作流，解决多个包互相依赖，且发布需要手动维护多个包的问题
- yarn

### MultiRepo

- 优点： 各模块管理自由度高，可自行选择构建工具，依赖管理，单元测试等配套设施
        各模块仓库统计一般不会太大

- 缺点： 仓库分散不好找、当有很多时、更加困难，分支管理混乱
        版本更新频繁，如果公共模块的版本发生了变化，需要对所有的模块进行依赖的更新
        CHANGELOG梳理异常折腾，无法很好的自动关联各个模块的变动联系，基本靠口口相传


### MonoRepo
- 优点： 一个仓库维护多个模块，不用到处找仓库
        方便版本管理和依赖管理，模块之间的引用、调试都非常方便，配合相应工具，可以一个命令搞定
        方便统一生成CHANGELOG，配合规范，可以在发布时自动生成CHANGELOG

- 缺点： 统一构建工具、对构建工具提出了更高要求、要能构建各种相关模块
        仓库统计会变大


```
npm i lerna -g
lerna init
```

## 创建包

```
yarn install
lerna create create-react-app2
lerna create react-script2
lerna create cra-template2
```

### 查看安装信息

```
yarn workspaces info

```

> yarn workspace 和 lerna
    有很多功能是重复，相等的


- yarn  重点在于包管理，处理依赖，处理软链接
- yarn install = lerna bootstrap
- lerna重点在于多个项目管理和发布


## 安装

```
yarn workspace create-react-app2 add commander

```