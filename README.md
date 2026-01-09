<div align="center">

# 🏴‍☠️ PXE-Arsenal: 移动终极引导站

[![Go 版本](https://img.shields.io/badge/Go-1.24-00ADD8?style=for-the-badge&logo=go)](https://golang.org/)
[![平台](https://img.shields.io/badge/平台-Android%20%7C%20Termux-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://termux.com/)
[![构建状态](https://img.shields.io/badge/状态-已编译%20Stable-brightgreen?style=for-the-badge)]()

> **"让你的安卓手机，成为顶尖的单兵系统部署中心。"**

[ **立即下载** ](https://github.com/Huaming007/PXE-Arsenal/releases) • [ **提交反馈** ](https://github.com/Huaming007/PXE-Arsenal/issues)

</div>

---

## 🚀 性能实战 (Adreno 740 平台)

基于 **骁龙 8 Gen 2** 物理环境的实测传输数据：

| 环境 | 模式 | 传输速度 | 稳定性 |
| :--- | :--- | :--- | :--- |
| **WiFi 7 (BE)** | 5G/6G 直连 | **40MB - 80MB/s** | 🟢 极高 (双机并发无压力) |
| **WiFi 6 (AX)** | 2.4G+5G 混合 | **10MB - 20MB/s** | 🟡 稳定 (DirectIO 深度优化) |

> **技术核心**：内置 **DirectIO** 与 **AIO Threads** 引擎。在高速下载 PE 镜像时，手机内存占用几乎为零，完美保护后台 LLM 模型运行。

---

## 🔥 核心武装 (Arsenal Features)

*   **📱 安卓原生优化**：内置 **WakeLock** 唤醒锁，彻底解决锁屏后 WiFi 降速、断流导致的引导失败。
*   **🛡️ 黑盒自修复**：`iPXE/Wimboot` 等核心引导文件内嵌在二进制程序中。目录被删？文件名改错？运行即刻自动复原。
*   **📡 智能分流**：全自动识别客户端 **BIOS/UEFI** 架构，秒级分发对应引导文件，实现“盲启动”。
*   **📂 逻辑分离弹药库**：
    *   **PE 极速通道**：针对 FirPE 深度调优，修复 UEFI 环境下常见的黑屏“玄学”。
    *   **Linux/工具 ISO**：放入 `linux` 目录，程序自动扫描并生成菜单，支持直接引导启动。
    *   **SMB 匿名镜像站**：内置 Samba 服务，Windows ISO 通过 `\IP\iso` 共享，装机无需复杂配置。

---

## 🛠️ 快速作战指南 (Quick Start)

### 1. 部署环境
下载 ZIP 包并解压到手机 (Termux/NetHunter) 的任意目录。

### 2. 填充资源
程序首次运行会生成目录，请按需放入文件：
- `tftpboot/win/` : 放入解压后的 WinPE 文件 (推荐 FirPE)。
- `tftpboot/linux/` : 放入 Linux 或维护工具 ISO。**[支持直接引导]**
- `tftpboot/iso/` : 放入 Windows 安装镜像。**[仅供 SMB 挂载]**

### 3. 开启火力
```bash
chmod +x pxe
./pxe
```

### 4. 客户端引导
- 电脑连接手机 WiFi。
- BIOS 开启 **PXE / Network Boot**。
- 见证手机引导电脑的瞬间。

---

## ⚠️ 实战注意事项

1.  **关于 Windows ISO**：由于系统限制，Windows 安装 ISO 不支持直接从菜单引导。请先进入 WinPE，然后通过 SMB 路径 `\你的手机IP\iso` 挂载安装。
2.  **电源管理**：虽然有唤醒锁，但在进行大规模系统部署时，建议手机连接充电器。

---

<div align="center">

**Developed with ❤️ by Huaming007**
*The World is Your 机房 (Server Room).*

</div>