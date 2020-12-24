# Code Review规范
## 目的
* 保证团队编码风格一致和代码可读性
* 保证代码质量，减少代码层面bug
* 相互提升
* 便于后期交叉维护

## CheckList
> CheckList 需不断添加完善
#### 1、代码规范检查
* 需依据[编码规范](https://github.com/yh-yunchuang-fe/yh-style-guide/blob/master/code.md)进行检查，检查是否有不符合规范的代码；
* 所有log删掉或注释掉，不应把log带上线；
* 没用到的方式和生命周期, 删掉；
* 测试数据, 假数据, 旧代码, 删掉. (部分可用于下一期开发的业务代码, 请做好 TODO标记, 避免误删)；
* 去掉被注释的代码（部分后续还可能使用的注释代码，需做好TODO标记，避免误删）；
#### 2、注释规范检查
* 注释需注明该段代码存在的原因（是为了解决什么问题）；
* 重要和复杂逻辑需写明设计思路；
* 对非常规行为和边界情况处理，添加描述/注释；
#### 3、性能检查
* 图片是否有放入CDN；
* 组件和节点的嵌套层级是否合理，是否可以减少嵌套层级；
* 需要异步处理的情况避免同步处理，以免影响主业务流程效率；
* 定时器、监控器是否有正常清除；
* setData是否有和渲染无关属性，层级是否嵌套过深，避免重复setData;
#### 4、代码质量
* 参数过多时，可转化为对象传参，否则一个方法的参数要加大代码的可维护性；
* 有没有错误处理，是否有考虑边界问题；
* 是否有非空判断；
* 重复造轮子的问题，对于已经有的公共代码，是否有复用；
* api使用是否合理，比如应该使用map的，却使用了forEach；

## Review操作规范
#### 1、对事不对人
    review评价中只对代码进行评价，不能关联到人；
#### 2、每次PR内容一定要少，建议少于300行/PR
    Code Review 效果和质量与 PR 代码量成反比，每次 PR 代码量小一些，看起来速度快，又不至于失去耐心，这样才能达到 Code Review 的效果，所以要经常进行 Code Review，但是每个 PR 代码量要少。  
    对于大的需求可以开两个分支，一个作为开发分支，一个作为合并分支，在开发分支完成一项可交付模块时就可提交一个PR，进行Review合并到合并分支；
#### 3、在提交Review前自己先Review一遍
#### 4、意见必须明确，不要出现我觉得你写的不好，但是怎么改进我也不知道。要不不要给意见，要不就要给清晰的意见
#### 5、对应项目的PR发到对应的PR群
    目前项目分为永辉生活小程序、超级物种小程序、CMS可视化建站、H5项目
#### 6、PR需要找到对应的模块负责人来进行Review
