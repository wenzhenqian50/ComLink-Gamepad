# ComLink-Gamepad: 万能控制器
---
![Windows Experimental](https://img.shields.io/badge/Windows-Experimental-orange?logo=windows&logoColor=white) [![ESP-IDF v5.5.1](https://img.shields.io/badge/ESP--IDF-v5.5.1-%23E7352C?logo=espressif&logoColor=white)](https://docs.espressif.com/projects/esp-idf/en/v5.5.1/esp32/get-started/index.html) [![ROS2 Humble](https://img.shields.io/badge/ROS2-Humble-22314E?logo=ros&logoColor=white)](https://docs.ros.org/en/humble/index.html) ![Vue.js](https://img.shields.io/badge/Vue.js-v3-%234FC08D?logo=vue.js&logoColor=white) ![Vant](https://img.shields.io/badge/Vant-UI-%231989FA?logo=vant&logoColor=white) [![License](https://img.shields.io/github/license/wenzhenqian50/ComLink-Gamepad)](LICENSE) ![GitHub stars](https://img.shields.io/github/stars/wenzhenqian50/ComLink-Gamepad?logo=github&color=yellow) [![Bilibili](https://img.shields.io/badge/Bilibili-homepage-%23FB7299?logo=bilibili&logoColor=white)](https://space.bilibili.com/493340537?spm_id_from=333.1007.0.0)

![渲染图](Docs/Images/ComLink.png)
> 注: 此仓库提供ComLink项目包括软硬件全部资源,仅用于学习,禁止商用.  
> Video URL: 

### 📈软件开发进度:
- [x] **HID 蓝牙设备模拟**
  - [x] 手柄
  - [x] 键盘
  - [x] 鼠标
  - [x] 多媒体
- [x] **ROS2 中数据交换**
  - [x] 发布手柄话题数据
  - [ ] 接收 Agent 反馈数据(屏幕查看/触发震动)
- [x] **ESP-NOW 与接收机互通**
  - [x] 广播通讯
  - [x] 点对点通讯
- [x] **Web 网页终端**
  - [x] 手柄数据可视化
  - [x] 手柄功能测试
  - [x] 参数配置与保存

### 📅TODO:
- 有线模式: 接入 **Agent 上位机**(类似Openclaw), Agent 借助控制器内置的 ESP-NOW 或 ROS2 的通讯通道, 实现对下位机(机器人)的控制接管.

# 项目介绍
### 简介:
之所以做这个项目是因为在平时做机器人或嵌入式开发中更多的是专注于控制部分, 上电运行测试或调试常常是直接使用板载开关手动操作(操作受限)或借助无线串口模块用键盘操作(不够优雅), 为了解决前面的痛点, 本着造轮子就要造个大的的态度, 就有了这一版的万能控制器; 得益于 ESP32 优秀的生态, 使用底层的WiFi/BLE协议栈构建起各式各样的连接方式, 真正实现了 **Com(共)Link(连)** 的目标🌟.
### 关于结构:
![全家福](Docs/Images/All_Body.png)
手柄外观设计灵感来源于 Switch 的 Joy-Con 手柄, 我第一次看到时就被它极具创新的连接与交互方式吸引到了, 并将其部分设计理念运用到了该项目;

**模块与个性化:** 通过顶部凸槽的磁吸连接器可以轻松的连接充电底座; 控制器整体设计尽可能保证对称和整洁, 使其便于 DIY 各式各样的拓展配件(握把/方向盘...), 咔哒! 即连!
>仓库添加了配备磁铁安装孔位的底板, 磁吸角度不再仅限于控制器顶部

**感知与交互:** 内部配置了六轴运动姿态传感器, 配备高精度滤波算法, 可以实现多样的交互方式, 还有震动马达加持(受限于空间利用, 没有使用线性马达, 待升级), 提供不错的触觉反馈.
![爆炸视图](Docs/Images/ComLink_Boom.png)
### 关于硬件
项目一共涉及到3块 PCB 的制作, 副板和底板负责用于拓展接口, 主板双面四层设计, 部分元件需要电烙铁焊接, 电源为一块400mAh的锂电池, 摇杆模块使用的Joy-Con同款拆机件; 主控使用ESP32S3N8R8, 板载CH343P和SGM4056用于串口转USB和电池充电保护, 配备长按开关机电路, 保证按键复用性与机身简洁, 采用双电源切换电路, 自由切换主机供电或电池供电.
![主板](Docs/Images/mainboard.PNG)
# 关于复刻

# 二次开发

