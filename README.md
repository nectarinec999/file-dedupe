# file.dedupe

file-dedupe 的飞牛 fnOS Native 应用打包工程。

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
