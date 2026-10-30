# VPS SSH 公钥

本仓库托管供 VPS 初始化导入的 SSH 公钥，不包含私钥。

- 公钥文件：`vps.pub`
- 类型：ED25519
- SHA256 指纹：`SHA256:gFSsWz8rzi9eV5S9chXhzHjTQ05t0/N3dGP9Ck9P6k0`
- 公钥直链：https://raw.githubusercontent.com/AbahAx/ssh-keys/main/vps.pub

下载公钥并核对指纹：

```bash
curl -fsSL https://raw.githubusercontent.com/AbahAx/ssh-keys/main/vps.pub -o /tmp/vps.pub
ssh-keygen -lf /tmp/vps.pub -E sha256
```

如果使用 BeacherZ/key.sh，请在下载并检查脚本后，使用 URL 导入：

```bash
bash key.sh -u https://raw.githubusercontent.com/AbahAx/ssh-keys/main/vps.pub
```

该脚本的 URL 导入还会启用公钥认证并重启 SSH。默认采用追加模式；不要使用会清空已有授权的 `-o` 参数。

导入公钥后，仍需在 SSH 客户端使用与之配对的私钥。请保留当前会话，并新建 SSH 会话确认可以登录，再关闭原有登录方式。

这里提供的是执行时导入。修改或删除仓库内的公钥，不会自动更新或撤销已经写入各台 VPS 的授权。
