# file.dedupe

file-dedupe 的飞牛 fnOS Native 应用打包工程。

当前版本使用飞牛开放 API 的应用共享目录授权和路径语义转换能力，要求 fnOS `1.2.0401` 及以上、飞牛客户端 `1.34.0` 及以上。前端通过官方 SDK 的 `pickSharedFile` 一次完成扫描目录选择与共享授权；已授权范围内的子目录由应用自身浏览，只会列出授权根及其内部可读目录。后端使用 `trim.file.sharedAccess` Scope 校验实际访问范围，并通过 `trim.file.path` Scope 将内部路径转换成便于用户理解的展示路径。

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
