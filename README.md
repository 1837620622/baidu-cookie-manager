<div align="center">

<img src="https://img.shields.io/badge/%E7%99%BE%E5%BA%A6-Cookie%20Manager-2932e1?style=for-the-badge&labelColor=16161A" />
<img src="https://img.shields.io/badge/v4.0%20%E6%96%B0%E5%A2%9E-Web%E7%89%88%E8%B4%B4%E5%90%A7%E7%AD%BE%E5%88%B0%E5%8F%B0-2932e1?style=for-the-badge&labelColor=16161A" />

<br/>
<br/>

# `Baidu Cookie Manager`

<h3>百度 Cookie 全生命周期自动化引擎</h3>

**验证 → 注入 → 保活 → 封禁检测，一条命令全自动完成**

<br/>

```
  ____        _     _          ____ _  __
 | __ )  __ _(_) __| |_   _  / ___| |/ /
 |  _ \ / _` | |/ _` | | | || |   | ' /
 | |_) | (_| | | (_| | |_| || |___| . \
 |____/ \__,_|_|\__,_|\__,_| \____|_|\_\
```

> **5 端点严格验证，杜绝假成功 | TBS + Passport 双重前置检测 | 反检测 Selenium | 全平台 GUI**

<br/>

<a href="https://www.bilibili.com/video/BV1qTF8zFEyG/">
  <img src="./封面.png" alt="Baidu Cookie Manager 演示" width="780" />
</a>

<br/>

<a href="http://118.195.148.242:5678/">
  <img src="https://img.shields.io/badge/%E5%9C%A8%E7%BA%BF%E6%BC%94%E7%A4%BA-%E6%AD%A3%E5%9C%A8%E8%BF%90%E8%A1%8C-2932e1?style=for-the-badge&logo=chrome&logoColor=white" />
</a>

<br/>

<a href="https://www.bilibili.com/video/BV1qTF8zFEyG/">
  <img src="https://img.shields.io/badge/B%E7%AB%99%E5%AE%9E%E6%93%8D%E6%BC%94%E7%A4%BA-%E7%82%B9%E5%87%BB%E6%92%AD%E6%94%BE-00A1D6?style=for-the-badge&logo=bilibili&logoColor=white" />
</a>

</div>

<br/>

## 在线体验 / Live Demo

> **演示地址：http://118.195.148.242:5678/**（v4.0 网页版贴吧签到台，浏览器直接访问）

- 手机 / 电脑浏览器打开即用，无需安装
- 演示环境仅供功能体验，账号数据请勿写入

## 为什么需要它

| | |
|:---:|:---|
| **Cookie 频繁失效** | 百度 Cookie 隔三差五掉线，手动检查一个账号要点 4 个网页，账号一多根本忙不过来 |
| **验证全靠猜** | 打开网页能访问 ≠ 登录态有效，经常"看着在线，实际已掉"，签到发帖才发现全失败了 |
| **注入提心吊胆** | 手动替换 Cookie 容易出错串号，操作一遍几十个账号，身心俱疲 |

**本工具把「检查 + 保活 + 注入 + 检测」全部自动化，全程服务端真实验证，每次操作都有凭有据。**

<br/>

## 四大核心能力

<table>
  <tr>
    <td align="center" width="25%">
      <img src="https://img.shields.io/badge/-Verify%20%E9%AA%8C%E8%AF%81-blue?style=for-the-badge" /><br/><br/>
      <b>服务端双重验证</b><br/><br/>
      <code>TBS is_login 检测</code><br/>
      <code>Passport 302 检测</code><br/><br/>
      <sub>无效账号直接拦截<br/>不浪费一个请求</sub>
    </td>
    <td align="center" width="25%">
      <img src="https://img.shields.io/badge/-Inject%20%E6%B3%A8%E5%85%A5-green?style=for-the-badge" /><br/><br/>
      <b>反检测注入引擎</b><br/><br/>
      <code>Selenium CDP 注入</code><br/>
      <code>跨账号隔离防串号</code><br/><br/>
      <sub>注入即服务端验证<br/>杜绝假成功</sub>
    </td>
    <td align="center" width="25%">
      <img src="https://img.shields.io/badge/-KeepAlive%20%E4%BF%9D%E6%B4%BB-orange?style=for-the-badge" /><br/><br/>
      <b>5 端点严格保活</b><br/><br/>
      <code>Passport 中心</code><br/>
      <code>贴吧 TBS</code><br/>
      <code>网盘用户信息</code><br/>
      <code>贴吧关注列表</code><br/>
      <code>文库用户信息</code><br/><br/>
      <sub>每个端点独立验证登录态</sub>
    </td>
    <td align="center" width="25%">
      <img src="https://img.shields.io/badge/-Detect%20%E6%A3%80%E6%B5%8B-purple?style=for-the-badge" /><br/><br/>
      <b>封禁与掉线检测</b><br/><br/>
      <code>结构级深度分析</code><br/>
      <code>全站权限矩阵</code><br/>
      <code>封禁特征识别</code><br/><br/>
      <sub>掉线原因一目了然</sub>
    </td>
  </tr>
</table>

<br/>

## 凭什么说「杜绝假成功」

传统工具检查 Cookie 只看"能不能打开百度首页"——首页 200 不代表登录有效，这就是假成功的根源。

**本工具采用 5 端点严格验证，每个端点独立校验登录态：**

| 百度产品 | 有效 BDUSS | 失效 BDUSS | 验证方式 |
|:---:|:---:|:---:|:---:|
| Passport 个人中心 | 200 | 302 跳转 | HTTP 状态码 |
| 贴吧 TBS | `is_login=1` | `is_login=0` | JSON 字段 |
| 网盘用户信息 | `errno=0` | `errno=-6` | JSON 字段 |
| 文库用户信息 | `code=0` | `code=200001` | JSON 字段 |
| 贴吧关注列表 | 200 | 302 跳转 | HTTP 状态码 |

```
前置验证(TBS+Passport) --> 5 严格端点 --> 随机延迟(1~3s) --> 最终验证
     |                        |              |                |
     +-- 无效直接拦截         +-- 每个端点    +-- 防风控策略    +-- 确认仍有效
     +-- 不浪费请求           +-- 独立验证    +-- Set-Cookie   +-- 杜绝假成功
```

<br/>

## v4.0 新增：网页版贴吧签到台

> 在保活引擎之上，新增 **浏览器访问的 Web 管理界面**，一个服务同时管理 **签到 / 发帖 / 保活**。手机、电脑浏览器打开即用。

| 模块 | 功能 |
|:---:|:---|
| **关注 + 签到** | 搜索贴吧名一键完成关注 + 签到，逐账号实时展示 PASS/FAIL |
| **发帖台** | 发帖 / 回复 / 删帖 / 删楼四工位，走贴吧 PC 新接口（v10.7.8.0+） |
| **账号档案** | 批量导入（如流格式）、状态检测、管理密码保护删除 |
| **自动保活** | 后台线程每 5 分钟自动心跳，ECG 生命体征实时监控 |
| **签到台账** | 历史记录按吧汇总成功率，支持单条重签 / 清空 |
| **验证引擎** | TBS + Passport 双验证，签到遇验证码如实报告不伪造成功 |

```
浏览器 ──► Flask 服务 ──► TiebaCore (PC 新接口签名)
   │            │              │
   │       账号 JSON 库    关注/签到/发帖/删帖
   │       (RLock 线程安全)   0.3~0.8s 随机延迟
   │            │              │
   └── 自动保活线程(300s) ◄─── 5 端点心跳 + TBS
```

<br/>

## 实际运行效果

```
[keepalive] browser_account 轻量级保活...
  BDUSS验证通过，开始访问保活接口...
  [OK] Passport中心 (已登录, status=200)
  [OK] 贴吧TBS (已登录, is_login=1)
  [OK] 网盘用户信息 (已登录, errno=0)
  [OK] 贴吧关注列表 (已登录, status=200)
  [OK] 文库用户信息 (已登录, code=0)
  保活完成，访问 5/5 个接口，BDUSS验证有效

[keepalive] invalid_account 轻量级保活...
  BDUSS已失效，无法保活，需重新登录获取Cookie

[inject] browser_account Cookie注入登录...
  注入Cookie: BDUSS=laUWxyVFB1QjFo...
  登录验证通过 - BDUSS服务端验证有效
  Cookie注入登录成功!
```

<br/>

## 命令速览

```bash
# 检查 Cookie 有效性（4 方法交叉验证）
$ python baidu_ck_manager.py check

# 轻量保活（推荐日常使用）
$ python baidu_ck_manager.py keepalive

# Selenium 浏览器注入登录
$ python baidu_ck_manager.py login

# 浏览器深度刷新 Cookie
$ python baidu_ck_manager.py refresh

# 定时自动保活（默认每 6 小时）
$ python baidu_ck_manager.py schedule --interval 6

# 处理单个账号
$ python baidu_ck_manager.py single -i 0
```

<br/>

## 技术栈与兼容性

| 层级 | 技术 |
|:---:|:---|
| **运行环境** | `Python 3.8+` |
| **GUI 界面** | `CustomTkinter` 暗色科技风 |
| **HTTP 客户端** | `Requests 2.31+` |
| **浏览器自动化** | `Selenium 4.15+` + Chrome DevTools Protocol |
| **驱动管理** | ChromeDriver Auto（Selenium 4.6+ 内置） |
| **数据持久化** | JSON + TXT 双格式备份 |
| **兼容平台** | macOS / Linux / Windows |

<br/>

## 项目结构

```
baidu-cookie-manager/
|
+-- baidu_ck_manager.py           # 核心引擎 (验证/注入/保活/封禁检测)
+-- baidu_ck_gui.py               # GUI 界面 (CustomTkinter 暗色科技风)
+-- test_single_ck.py             # BDUSS 深度测试 (结构分析/全站权限矩阵)
+-- ruliu_to_standard_bduss.py    # 如流账号转标准 BDUSS (Selenium 自动登录)
+-- requirements.txt               # 依赖: selenium, requests, customtkinter
+-- 待保活.txt                      # 输入: 账号 + Cookie 数据
+-- 保活成功.txt                    # 输出: 有效账号 + 保活时间戳
+-- cookies_backup.json            # 输出: JSON 格式完整备份
+-- baidu_ck.log                   # 运行日志 (含时间戳)
```

<br/>

---

<div align="center">

## 获取完整源码

<br/>

<img src="https://img.shields.io/badge/%E6%BA%90%E7%A0%81-%E4%BB%98%E8%B4%B9%E8%8E%B7%E5%8F%96-FF4444?style=for-the-badge" />

<br/>
<br/>

**本仓库仅提供项目说明与演示视频**

**完整源代码为付费内容（v3.0 桌面保活引擎 + v4.0 网页签到台），购买后提供一对一技术支持**

<br/>

<table>
  <tr>
    <td align="center"><b>源码包含</b></td>
    <td align="center"><b>源码包含</b></td>
    <td align="center"><b>源码包含</b></td>
    <td align="center"><b>源码包含</b></td>
  </tr>
  <tr>
    <td align="center"><code>完整源码</code></td>
    <td align="center"><code>使用指导</code></td>
    <td align="center"><code>部署协助</code></td>
    <td align="center"><code>后续更新</code></td>
  </tr>
</table>

<br/>
<br/>

| | |
|:---:|:---|
| **作者 Author** | **传康kk** |
| **微信 WeChat** | `1837620622` |
| **B站 Bilibili** | [传康kk](https://space.bilibili.com/) |
| **CSDN** | [万能程序员](https://blog.csdn.net/) |

</div>

<br/>

## 免责声明

本工具仅供学习和研究使用。使用时请遵守百度的服务条款和相关法律法规，因不当使用造成的任何后果由使用者自行承担。
