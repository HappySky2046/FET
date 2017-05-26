>Google的原则：不作恶。

>程序员的原则：不挖坑。

>写代码的正确方式：**战战兢兢，如履薄冰。**

## 前言
程序员是一个创造力强，个人色彩浓厚的职业，不同的人，代码的风格习惯千差万别，这个时候，就需要标准来约束程序员的代码，越是庞大的项目越应该如此。规范越早引入越好，规范的约束永远不嫌多。

## 好的原则
> 我们应该遵循古老的原则：“能做并不意味着应该做”。
- 约定优于配置
- 不要太过于依赖注释，注释只是业务的补充，**良好的代码结构和命名**能够能够避免很多不必要的注释
- 清晰原则：清晰胜于技巧 （代码是给人看的，其次才是在机器上运行的，10行复杂的代码不如30行清晰的代码）
- 吝啬原则：除非确无它法,不要编写庞大的程序（动不动就上千行的代码不要再出现了！！！）
- 健壮原则：健壮源于透明和简洁


## 命名规范
### 文件及目录
- 目录结构：js目前是按照一级、二级页面划分的
- 目录：`aaa_bbb`，采用linux命名规范，因为window不区分大小写
- js文件:`aaaBbb`，驼峰命名法
- 组件文件（特别是单文件组件）：`AaaBbb`,大写的驼峰命名法
- css：`aaa_bbb.css`，`aaa_bbb.scss`，`aaa_bbb.less`
- **争议** ：二级页面的样式文件放在css下面还是就近放在二级页面的目录下。

### 变量
- class：`aaa-bbb`
- 常量：`AAA_BBB`
- 函数：`aaaBbb(){}` 动词+定语（形容词）+宾语（名词）） 比如getResponse，sendRequest
- 类名 `class AaaBbb`
- 变量声明，`let`与`const`。
    - 尽量使用`const`。
    - 只有在变量值会改变的情况下使用`let`声明。

### action，store，路由等
- 路由：和目录结构统一。
- `store`：目录结构+下划线如`/order/indent`->`order_indent`。
- `action`的方法名须有该模块（目录）的前缀,保证唯一性。后面采恭动词+名词的形式。小写下划线方式连接。用如`/order/indent`下的action,获取订单模板：`order_indent_get_template_list`，
- `actionType`的常量须有该模块的前缀。
- `reduers`的名字须有该模块的前缀，同actions，小写下划线方式连接。
- 以上如果太长则使用缩写，如服务时间管理`Service_Mission_Manage`缩写是SMM。
- `react-route`的path用小写，_连接单词`<Routepath="service_mission_manage">。

> Tips：3是一个很奇妙的数字，目录结构，对象设计，路由层次等，尽量不要超过3层，超过3层时慎重考虑，保证工程的**扁平化**

### 常用缩写
**遵循通用规范，只使用显而易见的缩写，不要滥用，不要有歧义。**

| 变量名 | 常用缩写 |
| -- | -- |
| application | app | 
| arguments | args | 
| average | avg | 
| address | addr | 
| authority / authorize | auth | 
| attribute | attr | 
| asynchronization | asyn | 
| button | btn | 
| buffer | buff | 
| command | cmd | 
| compare | cmp | 
| calculate | calc | 
| calendar | cal | 
| character | char | 
| delete | del | 
| document | doc | 
| define | def | 
| develop | dev | 
| department | dept | 
| different | diff | 
| directory | dir | 
| dictionary | dict | 
| duplicate / duplication | dup | 
| dependency / dependent / depends | dep | 
| error | err | 
| escape | esc | 
| environment | env | 
| educate / education | edu |
| equal / equality / equivalence / equivalent | eq |
| frequency | freq | 
| government | gov | 
| information | info | 
| initialize | init | 
| individual | indv | 
| image | img | 
| escpae | esc | 
| length | len | 
| message | msg | 
| maximum | max | 
| minimum | min | 
| navigation | nav | 
| number | num | 
| object | obj | 
| operator | opr | 
| organization | org | 
| picture | pic | 
| previos | pre | 
| package | pkg | 
| parameter | param | 
| password | pwd | 
| position | pos | 
| properties | props | 
| request | req | 
| response | rsp | 
| record | rec | 
| reference | ref | 
| register | reg | 
| resource | res | 
| receive / received | recv | 
| string | str | 
| source | src | 
| standard | std | 
| statistic | stat | 
| student | stu | 
| summation / summary	 | sum | 
| system | sys | 
| system | sys | 
| sequence | seq | 
| synchronize | sync | 
| temporary | tmp/temp | 
| translate | trans | 
| user | usr | 
| utility | util | 
| variable | var | 
| window | win | 


## 数据处理
### 使用moment.js进行日期处理
```
moment("12-25-1995", "MM-DD-YYYY");
moment("2010-10-20 4:30", "YYYY-MM-DD HH:mm");
moment().format("dddd, MMMM Do YYYY, h:mm:ss a");
```

### 价格处理(后面可能上)
使用big.js进行价格处理
```
0.1 + 0.2                  // 0.30000000000000004
x = new Big(0.1)
y = x.plus(0.2)            // '0.3'
Big(0.7).plus(x).plus(y)   // '1.1'
```

## 分支管理与命名（暂定）
在后台不明确的情况下，前端请严格遵循`Git Flow`工作流规范。
![image](http://upload-images.jianshu.io/upload_images/1416338-2b5d1a64e15419d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- feature分支：feature+需求号，如`feature1916`
- release分支：release+需求号，如`release1916`

## commit message规范（试行）
社区有多种 Commit message 的写法规范，其中[Angular](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#heading=h.greljkmo14y0) 规范是目前使用最广的写法。不过，在现有团队中推行严格意义上的commit 规范还是有点太重了，因此暂时定一些简单的规则，特别是在master分支，建议遵守。
基本格式为：
```
type:(scope影响的范围)subject本次commit的简短描述
<br>
body 如果scope和subject不能描述清楚，在这里详述。
```


- 改bug：fix: bug号+bug标题  如：fixe: 13175 【管理端】【采购订单】修改采购订单页面，修改供应商后，保存报错 
- 添加新功能：feat: balabalabala
- 修改文档：docs: balabalabala
- 修改样式：style: （可能会影响的地方）修改的样式
- 代码重构：refactor: （可能会影响的模块或业务流程）重构的内容
- 优化：perf: 优化的内容+可能会影响的模块或业务流程  如：pref: (侧边菜单样式)样式优化，增大了菜单的点击区域。
- 构建工具的修改或优化等：build: 修改的内容或新增的功能
- 当前 commit 用于撤销以前的 commit: revert:reverts commit + hash + 撤销的commmit的标题
- 修改了其他的不影响业务东西，且不属于上面任何一种情况：chore：balabala

- 集成工具：ci: 暂时涉及不到
- 测试用例：test: 暂时涉及不到

## 编码规范
基于以下编码规范定制。
- [JavaScript编码规范](https://github.com/77ircloud/FET/wiki/JavaScript%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83)
- [React JSX 编码规范](https://github.com/77ircloud/FET/wiki/React-JSX-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83)

## 编码规范校验
暂时是主要基于下面两个定制的，后期将独立成单独的包。提交的代码必须要通过`eslint`及`stylelint`的校验。

- React校验 [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)
- css/scss校验 [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)

## Code Review规范（待完善）
