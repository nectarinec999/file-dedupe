# file.dedupe

file-dedupe 的飞牛 fnOS Native 应用打包工程。

当前版本使用飞牛开放 API 的应用共享目录授权能力，要求 fnOS `1.2.0401` 及以上、飞牛客户端 `1.34.0` 及以上。应用通过 `trim.file.sharedAccess` Scope 调用系统目录选择器，并由后端查询已授权目录。

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
