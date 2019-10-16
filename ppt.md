## **`console`调试--`network`**

- 空格键翻页
- 左右键切换页面，上下键翻章节
- esc 章节预览

<hor />
### Network 面板概览

<ver />
![network](/assets/1.png)

<ver />
1. `Controls`使用这些选项可以控制 `Network` 面板的外观和功能。
2. `Filters`使用这些选项可以控制在 `Requests Table `中显示哪些资源。**提示：按住 `Cmd (Mac)` 或 `Ctrl (Windows/Linux)` 并点击过滤器可以同时选择多个过滤器。**
3. `Overview` 此图表显示了资源检索时间的时间线。如果您看到多条竖线堆叠在一起，则说明这些资源被同时检索。

<ver />
4. `Requests Table`此表格列出了检索的每一个资源。 默认情况下，此表格按时间顺序排序，最早的资源在顶部。点击资源的名称可以显示更多信息。 **提示：右键点击 Timeline 以外的任何一个表格标题可以添加或移除信息列。**
5. `Summary` 此窗格可以一目了然地告诉您请求总数、传输的数据量和加载时

<hor />

#### 记录网络活动与屏幕截图

<ver />

记录网络活动：显示红色 (记录按钮打开) 表明 DevTools 正在记录。 显示灰色 (记录按钮关闭) 表明 DevTools 未在记录。

<ver />
![network](/assets/2.png)

<hor />

#### 查看 `DOMContentLoaded` 和 `load` 事件信息

<ver />

- 解析 HTML 结构。
- 加载外部脚本和样式表文件。
- 解析并执行脚本代码。
- 构造 HTML DOM 模型。// DOMContentLoaded 相当于 jQuery 中的 ready
- 加载图片等外部文件。
- 页面加载完毕。// load

<ver />

![network](/assets/3.png)

<hor />

### 查看单个资源的详细信息

<ver />

#### `查看 HTTP 标头`

Headers 标签可以显示资源的请求网址、HTTP 方法以及响应状态代码。 此外，该标签还会列出 HTTP 响应和请求标头、它们的值以及任何查询字符串参数

<ver />

#### `预览资源`

点击 Preview 标签可以查看该资源的预览。Preview 标签可能显示一些有用的信息，也可能不显示，具体取决于您所选择资源的类型

<ver />

#### `查看 HTTP 响应内容`

点击 Response 标签可以查看资源未格式化的 HTTP 响应内容。 Preview 标签可能包含一些有用的信息，也可能不包含，具体取决于您所选择资源的类型。

<ver />

#### `查看网络耗时`

点击 Timing 标签可以查看单个资源请求生命周期的精细分解。
生命周期按照以下类别显示花费的时间：

Queuing
Stalled
如果适用：DNS lookup、initial connection、SSL handshake
Request sent
Waiting (TTFB)
Content Download

<ver />

如果网络异常更加详细的各流程耗时这一点很重要

![network](/assets/4.png)

<hor />

#### 查看 Cookie

点击 Cookies 标签可以查看在资源的 HTTP 请求和响应标头中传输的 Cookie 表。 只有传输 Cookie 时，此标签才可用

<hor />

#### 查看 WebSocket 框架

点击 Frames 标签可以查看 WebSocket 连接信息。只有选定资源发起 WebSocket 连接时，此标签才会显示

<hor />
#### 查看资源发起者和依赖项
**按住 Shift 并将鼠标悬停在资源上**，可以查看其发起者和依赖项。 本部分将您悬停的资源称为目标。目标上方的第一个绿色编码资源为目标的发者如果上方存在第二个也是绿色编码的资源，那么该资源将是发起者的发起者。 目标下方红色编码的任何资源都是目标的依赖项。
<ver />

![network](/assets/5.png)

<hor />

#### 调试技巧

<ver />

Network 面板中的 initiator 列显示了是哪个脚本的哪一行触发了请求。他显示了在调用堆栈中触发请求的最后一步，除非你用的是，例如：一个本地化的 fetch API,它将会指向一些低层级的类库的代码.
<ver />

![network](https://user-gold-cdn.xitu.io/2018/12/29/167f8282477941b8?imageslim)

<ver />

在请求表中，你可以看到有关每个请求的几条信息，例如：Status, Type, Initiator, Size 和 Time 。
<ver />

![network](https://user-gold-cdn.xitu.io/2018/12/29/167f828279b0b397?imageslim)
<ver />
Network 面板中的过滤器输入可以接受你输入的字符串或正则表达式，仅显示匹配的请求。 但是你也可以使用它来过滤很多属性。
只需输入 例如 method 或者 mime-type :
