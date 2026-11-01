# 第三方组件许可声明

PulseDesk 使用了以下开源组件。本文件列出每个组件的名称、许可证类型与来源，
以履行各许可证的署名要求。

**分发本软件（无论是否修改）时必须同时分发本文件。**

---

## 组件清单

### MPL-2.0（Mozilla Public License 2.0）

| 组件 | 用途 | 来源 |
|---|---|---|
| LibreHardwareMonitorLib | 硬件传感器读取（温度、电压、风扇） | https://github.com/LibreHardwareMonitor/LibreHardwareMonitor |
| RAMSPDToolkit-NDD | 内存条 SPD 信息读取 | https://github.com/Blacktempel/RAMSPDToolkit |
| DiskInfoToolkit | 硬盘 SMART / 型号信息 | https://github.com/Blacktempel/DiskInfoToolkit |
| BlackSharp.Core | 上述组件的公共依赖库 | https://github.com/Blacktempel/BlackSharp |

MPL-2.0 是**文件级** copyleft：允许闭源使用与分发，但如果你修改了这些组件的
源文件，修改后的文件必须以 MPL-2.0 公开。本项目**未修改**上述组件，
仅以未修改的二进制形式引用。

许可证全文：`licenses/MPL-2.0.txt`

---

### MIT

| 组件 | 用途 | 来源 |
|---|---|---|
| OxyPlot | 绘图库（依赖项） | https://github.com/oxyplot/oxyplot |
| OxyPlot.WindowsForms | OxyPlot 的 WinForms 后端 | https://github.com/oxyplot/oxyplot |
| Microsoft.Win32.TaskScheduler | 计划任务创建与管理 | https://github.com/dahall/TaskScheduler |
| Microsoft.Diagnostics.Tracing.TraceEvent | ETW 事件解析 | https://github.com/microsoft/perfview |
| Microsoft.Diagnostics.FastSerialization | ETW 序列化（perfview 组件） | https://github.com/microsoft/perfview |
| OSExtensions | ETW 辅助（perfview 组件） | https://github.com/microsoft/perfview |
| Microsoft .NET 基础类库 | .NET 运行时类库 | https://github.com/dotnet/runtime |

MIT 允许闭源商用，只需保留版权声明与许可证文本。

许可证全文：`licenses/MIT.txt`

---

### BSD-3-Clause

| 组件 | 用途 | 来源 |
|---|---|---|
| psutil | Python 侧的系统信息采集（CPU、内存、网络、进程） | https://github.com/giampaolo/psutil |
| Aga.Controls | 树形控件（LibreHardwareMonitor 的依赖项） | https://sourceforge.net/projects/treeviewadv/ |

BSD-3-Clause 允许闭源商用，需保留版权声明、许可证文本，
且**不得用原作者名义为衍生品背书**。

许可证全文：`licenses/BSD-3-Clause.txt`（psutil 的版权行见 `licenses/BSD-3-Clause-psutil.txt`）

---

### Apache-2.0

| 组件 | 用途 | 来源 |
|---|---|---|
| HidSharp | USB HID 设备访问（读取部分硬件传感器） | https://github.com/IntergatedCircuits/HidSharp |

Apache-2.0 允许闭源商用，需保留版权声明、许可证文本，并**声明是否修改过文件**。
本项目未修改该组件。

许可证全文：`licenses/Apache-2.0.txt`

---

### LGPL-3.0 ⚠️ 需注意

| 组件 | 用途 | 来源 |
|---|---|---|
| pystray | 系统托盘图标 | https://github.com/moses-palmer/pystray |

**这是本项目中唯一需要特别履约的许可证。**

LGPL-3.0 允许闭源程序使用该库，但要求：**最终用户能够替换这个库的版本**，
并且能够反向工程调试这种替换。

本项目通过 PyInstaller 打包满足该要求：pystray 以**独立模块**形式
存在于打包产物中（而非静态编译进主程序二进制），用户可以用自己的 pystray 版本
替换后重新运行。同时本文件与 `licenses/LGPL-3.0.txt` 提供了许可证全文。
使用许可协议（LICENSE）第五节明确保留了为替换该库而反向工程的法定权利。

如果你要把本项目改造成**完全单文件静态链接**的形式，需要重新评估此项合规性。

许可证全文：`licenses/LGPL-3.0.txt`

---

### GPL-2.0-or-later WITH Bootloader-exception

| 组件 | 用途 | 来源 |
|---|---|---|
| PyInstaller | 打包工具（bootloader 部分被嵌入 exe） | https://pyinstaller.org/ |

PyInstaller 本身的 GPL 带有 **Bootloader Exception**：明确允许将 bootloader
嵌入并分发**任意许可证**的应用程序，不要求应用程序开源。因此用它打包闭源
商业软件是合规的。

本项目仅将 PyInstaller 用作构建工具，其 Python 代码部分不会进入最终产物。

许可证全文：`licenses/GPL-2.0-with-bootloader-exception-PyInstaller.txt`

---

### MIT-CMU（Pillow 专用）

| 组件 | 用途 | 来源 |
|---|---|---|
| Pillow (PIL) | 图像处理（皮肤背景、图标缩放） | https://python-pillow.org/ |

Pillow 使用 MIT-CMU 许可证（MIT 的变体，额外禁止用 Imaging 名称背书）。

许可证全文：`licenses/MIT-CMU-Pillow.txt`

---

### PSF-2.0

| 组件 | 用途 | 来源 |
|---|---|---|
| Python | 运行时（被 PyInstaller 打包进 exe） | https://www.python.org/ |

Python 使用 PSF License Agreement，允许再分发（含二进制形式），
需保留许可证文本与版权声明。

许可证全文：`licenses/PSF-Python.txt`

---

## 分发检查清单

如果你要分发本软件（原版或修改版），确认：

- [ ] 保留了 `licenses/` 目录下的全部许可证全文
- [ ] 保留了程序内「关于 → 开源许可」页面
- [ ] 保留了本文件（`THIRD-PARTY-NOTICES.md`）
- [ ] 未声称对上述第三方组件拥有版权
- [ ] 未用原作者名义为你的产品背书
- [ ] 若修改了 MPL-2.0 组件的源文件，已公开修改后的文件
- [ ] 保持了 pystray 的可替换性（见上文 LGPL 说明）

---

## 本文档的权威性

本文件中的许可证全文取自：

- psutil / Pillow / pystray / PyInstaller / Python：**本机安装包自带文件**
- Apache-2.0 / MPL-2.0 / LGPL-3.0：**官方站点下载**
- MIT / BSD-3-Clause：**SPDX 标准文本**

比网络二手转载更可靠。如需核对，各组件来源链接已列在上表中。

---

*本文档随软件版本更新。当前对应 PulseDesk 1.0.0。*
