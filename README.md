# file.dedupe

file-dedupe 的飞牛 fnOS Native 应用打包工程。

当前版本使用飞牛开放 API 的目录选择、文件页面路由和路径语义转换能力，要求 fnOS `1.2.0401` 及以上、飞牛客户端 `1.34.0` 及以上。点击新建任务后，前端会直接通过官方 SDK 的 `pickSharedFile` 打开目录选择器；用户选择的具体文件夹会自动加入扫描范围。任务详情可通过 `openFileManager` 打开文件所在目录，也可通过 `openFile` 交给飞牛尝试打开文件。个人路径统一从 `/我的文件` 开始展示。删除磁盘文件后仍会保留并置灰本次扫描记录。后端使用 `trim.file.sharedAccess` Scope 对最终路径进行强制校验，并通过 `trim.file.path` Scope 将内部路径转换成便于用户理解的展示路径。

仓库已经包含：

- `app/server/file-dedupe-server`：Linux amd64 Go 后端
- `app/www`：Vue 生产构建资源
- `app/ui`：桌面入口和统一网关配置
- `cmd`：应用生命周期与卸载脚本

因此克隆本仓库后可以直接打包：

```bash
fnpack build
```

生成的 FPK 文件不会提交到 Git。
