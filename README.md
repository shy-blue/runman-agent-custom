# Runman Agent (自定义全功能增强版)

本仓库提供经过定制与深度优化的 **Runman Agent** 二进制程序与一键无损安装/升级脚本。

## 🌟 核心特性
- **本地自用实例隔离**：支持在本地管理面板创建属于自己的自用小鸡，**不上报平台、不进入平台计费与控制**。
- **支持开满 5 台 128MB 小鸡**：针对 1G/768M 内存母鸡进行底座内存阈值放宽与内核调优。
- **内置 512MB ZRAM 内存实时压缩**：系统级集成 ZRAM 压缩块设备（优先级 100），大幅提升内存利用率，杜绝 OOM。
- **凭据持久化与一键复制**：自用小鸡创建/重装生成的 root 密码保存在本地，面板支持直接点击「显示」与「复制」密码、一键复制 SSH 命令。
- **SSH 端口自动纠偏**：避免因重装系统导致的内部端口错位（自动对齐内部 22 端口）。
- **100% 兼容平台**：与独角鲸/Narwhal 平台无缝协作，平台指令与上报完全不受任何干扰。

---

## 🚀 安装与升级指南

### 场景 1：已有官方版本，【无损一键覆盖升级】
如果你的机器原来已经安装了官方版 Runman Agent，直接运行下方命令即可无损升级（**保留已有配置、保留已有平台实例、保留平台 Token，不需要重新输入任何信息**）：
```bash
curl -fsSL https://github.com/shy-blue/runman-agent-custom/releases/download/v0.1.6/install.sh | bash
```

### 场景 2：全新机器【一键全新接入安装】
如果在全新机器上安装，并直接接入独角鲸平台托管：
```bash
curl -fsSL https://github.com/shy-blue/runman-agent-custom/releases/download/v0.1.6/install.sh | bash -s -- --token <你的平台AGENT_TOKEN>
```

> **可选参数**：
> - `--token <TOKEN>`：独角鲸后台复制的 Agent Token。
> - `--user <USERNAME>`：管理面板用户名（默认 `admin`）。
> - `--pass <PASSWORD>`：管理面板登录密码。

---

## 💻 访问本地管理面板
安装/升级完成后，浏览器打开：
```text
http://<你的母鸡公网IP>:8792/
```
登录后即可享受自用实例创建与全部增强功能！
