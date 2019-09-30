## 关于魔改

其实就是把输出字符串改成了输出数组QAQ，没什么实质性改动。

这样可以方便地实现一些功能，比如随机顺序输出友链之类的。

## 使用方法

调用`Links_Plugin::output($pattern,$links_num,$sort);`函数，该函数返回一个数组。

其中`$pattern`是输出格式，`$links_num`是输出数量（默认全输出），`$sort`表示输出指定分类（默认不指定）。

输出格式表示每条友链的`html`代码，用`{}`表示友链信息（将会被解析替换），常用的如下：

- `{name}` - 友链名称
- `{url}` - 友链链接
- `{image}` - 友链图标
- `{description}` - 友链描述

MDUI2333中使用的格式如下：

```php
$Links=Links_Plugin::output('
	<div class="mdui-col">
		<div class="mdui-card mdui-m-y-1 mdui-hoverable">
			<a href="{url}" target="_blank">
				<div class="mdui-card-header">
					<img class="mdui-card-header-avatar" src="{image}" alt="{name}"/>
					<div class="mdui-card-header-title">{name}</div>
					<div class="mdui-card-header-subtitle">{description}</div>
				</div>
			</a>
		</div>
	</div>
');
```