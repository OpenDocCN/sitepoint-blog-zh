# HTML5 跨浏览器聚合填充初学者指南

> 原文：<https://www.sitepoint.com/html5-cross-browser-polyfills/>

网络看起来发展很快。新的框架、工具甚至语言来来去去。然而，许多开发人员认为他们必须和最慢的用户一样快。新的浏览器是“常青树”——它们在后台自动更新，无需征得许可，并且在开发新的 API 方面取得了长足的进步。

然而，即使是现代浏览器也是在不同的时间实现不同的功能。令人沮丧的是，读到现代发展的前沿，却想到未来几年都无法使用。也许你已经浏览了你网站的分析，发现用户仍然在使用 IE9？你应该像 2011 年那样编码，还是把一切都委托给 jQuery 或某个框架？还有另一个选择。*进入聚合填充*。

## 什么是 Polyfills，我们为什么需要它？

Remy Sharp 在 2009 年的一本书和博客文章中创造了这个术语。如果特征存在于浏览器中，聚合填充会让浏览器执行其任务，如果不存在，聚合填充会插入缺少的功能。它们填补了旧浏览器的漏洞，即我们今天想要使用的缺失功能。它用非本机代码复制本机 API。

## 我们说的是哪些缺失的功能？

2009 年，ECMAScript 第五版登陆。这是该语言向前迈出的一大步。ECMAScript 2015 提供了类似的地震更新。展望未来，这种语言的改进将逐年递增。这是一个激动人心的时代，新的特性不断地出现在语言中。除了核心语言本身，还有 web 平台的 DOM 和各种 API。

为了突出现代浏览器和传统浏览器之间的差异，这里有一个最新版本的 Chrome 与 Internet Explorer 9 的比较(遗憾的是，一些公司仍然强制支持 Internet Explorer 9)。这里有一个[表显示了对 ECMAScript 6](https://kangax.github.io/compat-table/es6/) 的支持。第二个表只能追溯到 IE 11，正如你所看到的，它几乎不支持 ES6 特性。这是很多缺失的功能…

## 多填料与传输填料

很明显，从上面的表格来看，我们需要转换我们的代码。它采用你崭新的语法，抛弃普通的老式 ECMAScript 5。如果你想在你的代码中利用 [arrow 函数](https://www.sitepoint.com/javascript-arrow-functions/)、async/await、rest 和 spread 参数、类等等，你需要用一个工具比如 [Babel](https://babeljs.io/) 把你的 ES6 代码转换成 ES5。

但是，您不能填充 JavaScript 的语法。虽然 Babel 会将你的 arrow 函数转换成常规函数，但 polyfill 会将方法添加到全局范围和本地原型中。Babel 提供了自己的 [ES6 polyfill](https://babeljs.io/docs/usage/polyfill/) ，用 Babel 网站的话说，它提供了“像`Promise`或`WeakMap`这样的新内置，像`Array.from`或`Object.assign`这样的静态方法，像`Array.prototype.includes`这样的实例方法，以及生成器函数。”

所以 Babel polyfill 可以给我们所有想要的 ES6 特性。但是它遗漏了很多。也许您可以用`classList` API 添加和删除类，或者用`matchMedia`进行媒体查询，但是您仍然需要支持 IE9。幸运的是，有一项服务可以提供 Babel polyfill 涵盖的所有内容，甚至更多。

## Polyfill.io 让生活更轻松

Polyfill.io 是英国《金融时报》开发的一项开源项目。它目前每天接收多达 2.04 亿个请求，并把自己描述为“一个规范的聚合填充库”。这种多填料按需交付系统使你能够细读*我能使用*吗，耸耸肩，使用最新的标准，并且仍然兼容传统的浏览器。

> 昨天对[@ polyfilio](https://twitter.com/polyfillio)的 2.04 亿次请求！打破了所有以前的记录。😅pic.twitter.com/tifoPGQptW
> 
> —爱丽丝·巴特利特(@ Alice Bartlett)[2017 年 5 月 24 日](https://twitter.com/alicebartlett/status/867278480542752768)