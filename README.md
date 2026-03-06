# openclaw_computer

一个预装 OpenClaw 并具有桌面环境的 Linux 容器，适配 ModelScope、HuggingFace 等免费容器部署服务，通过浏览器即可畅玩体验 OpenClaw

## 通过本项目，你将获得：
- 💻 一台硬件配置至少为2核/16GB内存的 Linux 云电脑（由 ModelScope/HuggingFace 免费提供）
- ✨ 具有类 Windows 桌面的系统操作环境，预装 Chrome 浏览器 / 中文拼音输入法，轻松易上手
- 🚀 开箱即用的 OpenClaw，默认配置 ModelScope 模型推理后端（免费），提供密钥即可畅玩

## 运行容器（ModelScope/HuggingFace Spaces）

在 Spaces 文件目录下添加 Dockerfile 文件，内容和本仓库中的 Dockerfile 文件保持一致，然后在“设置”中添加 `ROOT_PASSWD` 和 `MODELSCOPE_API_KEY` 两个环境变量，最后点击重启容器即可开始部署。

ModelScope API 密钥获取教程参见：[https://modelscope.cn/docs/accounts/token](https://modelscope.cn/docs/accounts/token)

## 运行容器（本地）

```bash
docker run -d \
  -p 7860:7860 \
  -e ROOT_PASSWD=123456 \
  -e MODELSCOPE_API_KEY=your_api_key_here \
  openclaw_computer:latest
```

## 环境变量配置

| 变量名 | 必填 | 默认值 | 说明 |
|--------|------|--------|------|
| `ROOT_PASSWD` | 否 | `123456` | root 用户密码，长时间未使用系统自动锁屏时需输入此密码解锁 |
| `MODELSCOPE_API_KEY` | 否 | `not_set_yet` | ModelScope API 密钥，用于 OpenClaw 模型服务，未设置时其将无法正常工作 |


## 帮助信息

- **输入法切换**：按 `Ctrl+Shift` 组合键切换中英文输入法
