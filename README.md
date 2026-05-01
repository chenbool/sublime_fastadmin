# sublime_fastadmin

> Sublime Text 语法提示插件，支持 FastAdmin 框架

## 功能特性

| 特性 | 说明 |
|------|------|
| 代码片段 | 30+ 个代码片段 |
| 完整覆盖 | 覆盖 FastAdmin 核心功能 |
| 智能提示 | 支持 Tab 键快速补全 |
| 后台管理 | 专为 FastAdmin 后台开发设计 |

## 安装

### Sublime Text 安装

1. 打开 Sublime Text
2. 按 `Ctrl+Shift+P` 打开命令面板
3. 输入 `Package Control: Install Package`
4. 搜索 `fastadmin` 并安装

### 手动安装

将项目克隆到 Sublime Text 的 Packages 目录：

```bash
git clone https://github.com/chenbool/sublime_fastadmin.git
```

## 代码片段总览

| 分类 | 数量 | 说明 |
|------|------|------|
| Controller | 3 | 控制器 |
| Model | 5 | 模型 |
| DB | 8 | 数据库操作 |
| Validate | 1 | 验证器 |
| JS | 2 | 前端控制器 |
| View | 10 | 视图模板 |

## 使用示例

```php
// 控制器
public function index() {
    if ($this->request->isAjax()) {
        list($where, $sort, $order, $offset, $limit) = $this->buildparams();
        $list = $this->model->where($where)->order($sort, $order)->limit($offset, $limit)->select();
        return json(['total' => count($list), 'rows' => $list]);
    }
    return $this->view->fetch();
}

// JS控制器
define(['jquery', 'bootstrap', 'backend', 'table'], function($, undefined, Backend, Table) {
    var Controller = {
        index: function() {
            Table.api.init();
        },
        api: { formatter: { status: function(value) { return value == 'normal' ? '正常' : '禁用'; } } }
    };
    return Controller;
});
```

## 相关项目

| 项目 | 仓库地址 |
|------|----------|
| sublime_swoole | https://github.com/chenbool/sublime_swoole |
| sublime_yaf | https://github.com/chenbool/sublime_yaf |
| sublime_thinkphp5 | https://github.com/chenbool/sublime_thinkphp5 |
| sublime_thinkphp6 | https://github.com/chenbool/sublime_thinkphp6 |
| sublime_thinkphp8 | https://github.com/chenbool/sublime_thinkphp8 |
| sublime_laravel | https://github.com/chenbool/sublime_laravel |
| sublime_workerman | https://github.com/chenbool/sublime_workerman |
| sublime_webman | https://github.com/chenbool/sublime_webman |
| sublime_fastadmin | https://github.com/chenbool/sublime_fastadmin |

## License

MIT License
