# file.dedupe

file-dedupe 的飞牛 fnOS Native 应用打包工程。

当前版本使用飞牛开放 API 的应用共享目录授权和路径语义转换能力，要求 fnOS `1.2.0401` 及以上、飞牛客户端 `1.34.0` 及以上。前端通过官方 SDK 的 `pickSharedFile` 一次完成扫描目录选择与共享授权；从已有授权范围选择时调用飞牛 `pickFile` 系统选择器，并传入后端生成的已知未授权路径黑名单。后端仍使用 `trim.file.sharedAccess` Scope 对最终路径进行强制校验，并通过 `trim.file.path` Scope 将内部路径转换成便于用户理解的展示路径。

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
