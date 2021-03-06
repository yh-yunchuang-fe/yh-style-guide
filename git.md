# Git规范
# Git提交规范
## 规范的作用
代码提交规范是为了让其他人能在最短的时间内知道每次提交的意义：  
* 每次提交影响的具体范围？
* 这个bug在哪次提交中被修复了？
* 这个新功能是在哪次提交中增加的？
* 修改是否向下兼容？
* 是否回滚了代码？
* 是否只是修改了文档、调整了代码格式？
* 是否修改了测试、是否进行了重构？
* 是否对代码进行了性能优化？

## 规范细则
有非常明确而详细的提交规范，有助于我们在查看项目历史时，更容易明确每一次提交的内容。另一方面，我们还直接使用了Git提交日志来生成变更日志。

### 提交消息格式
```
修改类型(影响范围): 标题
<--空行-->
[正文]
<--空行-->
[页脚]
```
* **标题是强制性的，但标题的范围是可选的。**
* **提交消息的任何一行都不能超过100个字符。**（让消息可以在各种Git工具中都更容易阅读）

### 修改类型
每个类型值都表示了不同的含义，类型值必须是以下的其中一个：  
* **feat**：新功能 feature
* **fix**：修复了bug
* **docs**：只修改了文档、注释
* **style**：调整代码格式，未修改代码逻辑（比如修改空格、格式化、缺少分号等）
* **refactor**：代码重构，既没修复bug也没有添加新功能
* **perf**：性能优化，提高性能的代码更改
* **test**：添加或修改代码测试
* **chore**：对构建流程或辅助工具和依赖库（如文档生成等）的更改
* **revert**：回退
* **build**：打包

### 影响范围
范围不是固定值，它可以是你提交代码实际影响到的任何内容。例如首页、楼层组件、API层、状态管理等，唯一需要注意的是它必须足够简短。

### 标题
标题是对变更的简明描述：
* 以动词开头；
* 不要大写首字母；
* 结尾不要使用句号；

### 正文
正文部分是对本次 commit 的详细描述，可以分成多行。正文应该说明代码变动的动机，以及与以前行为的对比。

### 页脚
页脚部分只用于两种情况。  

**（1）不兼容变动**
如果当前代码与上一个版本不兼容，则 Footer 部分以BREAKING CHANGE开头，后面是对变动的描述、以及变动理由和迁移方法。  

**（2）关闭 Issue**
如果当前 commit 针对某个issue，那么可以在 Footer 部分关闭这个 issue 。  
例如：
```
Closes #234
// or
Closes #123, #245, #992
```

### 示例
![示例](https://github.com/yh-yunchuang-fe/yh-style-guide/blob/master/imgs/gitmessagedemo.jpg)