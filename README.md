# 🌅 Dawn Extension Bot [v1.6]

<div align="center">
  <img src="./console/images/console.png" alt="Dawn Extension Bot Console" width="600"/>
  
  <p align="center">
    <a href="https://t.me/JamBitPY">
      <img src="https://img.shields.io/badge/Telegram-Channel-blue?style=for-the-badge&logo=telegram" alt="Telegram Channel">
    </a>
    <a href="https://t.me/+u7hWfz0WqsFkNmMy">
      <img src="https://img.shields.io/badge/Telegram-Chat-blue?style=for-the-badge&logo=telegram" alt="Telegram Chat">
    </a>
  </p>
</div>

## 📋 目录
- [功能](#-功能)
- [要求](#-要求)
- [安装](#-安装)
- [配置](#%EF%B8%8F-配置)
- [使用](#-使用)
- [故障排除](#-故障排除)

## 🚀 功能

- ✨ **账户管理**
- ✅ 自动账户注册和登录
- 📧 智能账户重新验证系统
- 🛡️ 基于令牌的身份验证存储

- 🤖 **自动化**
- 🌾 智能任务完成
- 💰 优化积分耕种
- 🔄 高级保活系统

- 📊 **分析和导出**
- 📈 综合账户统计
- 📉 被禁帐户跟踪
- 📋 未经验证的帐户监控

- 🔒 **安全**
- 🧩 高级验证码解决集成
- 🌐 代理支持 (HTTP/SOCKS5)
- 🔐 安全电子邮件集成

## 💻 要求

- Python 3.11 或更高版本
- 稳定的互联网连接
- 有效的电子邮件帐户
- 工作代理 (HTTP/SOCKS5)
- 验证码服务订阅 (2captcha/anticaptcha)

## 🛠️ 安装

1. **克隆存储库**
```bash
git clone [存储库 URL]
```

2. **设置虚拟环境**
```bash
python -m venv venv
source venv/Scripts/activate # Windows
source venv/bin/activate # Unix/MacOS
```

3. **安装依赖项**
```bash
pip install -r requirements.txt
```

## ⚙️ 配置

### 📁 settings.yaml

```yaml
# 核心配置
threads: 30 # 并发操作线程（最小：1）
keepalive_interval: 120 # Keepalive 信号间隔（秒）
referral_codes: # 支持多个推荐代码
- "" # 在此处添加您的代码

# 邮件重定向设置
redirect_settings:
enabled: false # 启用/禁用邮件重定向
email: "test@gmail.com" # 重定向电子邮件地址
password: "password" # 邮件密码
imap_server: "imap.gmail.com"
use_proxy: true # 使用代理进行电子邮件操作

# 验证码配置
captcha_module: 2captcha # 选择：'2captcha' 或'anticaptcha'
two_captcha_api_key: "" # 2captcha API 密钥
anti_captcha_api_key: "" # Anticaptcha API 密钥

# 启动设置
delay_before_start:
min: 2 # 最小启动延迟（秒）
max: 3 # 最大启动延迟（秒）

# 电子邮件提供商设置
imap_settings:
# 全球提供商
gmail.com: imap.gmail.com
yahoo.com: imap.mail.yahoo.com
outlook.com: imap-mail.outlook.com
hotmail.com: imap-mail.outlook.com
icloud.com: imap.mail.me.com

# 区域提供商
mail.ru: imap.mail.ru
rambler.ru: imap.rambler.ru
gmx.com: imap.gmx.com
onet.pl: imap.poczta.onet.pl
```

### 📁 输入文件结构

#### accounts/register.txt
```
email:password
email:password
```

#### accounts/farm.txt
```
email:password
email:password
```

#### accounts/reverify.txt
```
email:password
email:password
```

#### proxies/proxies.txt
```
http://user:pass@ip:port
http://ip:port:user:pass
socks5://user:pass@ip:port
```

## 🚀 使用

1. 如上所述配置所有必需文件
2. 启动机器人：
```bash
python run.py
```

## ⚠️ 重要说明

- 🕒 建议的 keepalive 间隔：120 秒
- 📧 Gmail 用户：使用应用专用密码
- 🔄 未经验证的帐户可以使用注册模块重新验证
- 💾 授权令牌存储在本地数据库中
- 🤖 需要外部验证码服务 (2captcha/anticaptcha)

## 🔧 故障排除

### 常见问题和解决方案

#### 📧 电子邮件验证失败
- 验证 settings.yaml 中的 IMAP 设置
- 检查电子邮件提供商的安全设置
- 确保 Gmail 的应用专用密码

#### 🧩 验证码问题
- 验证 API 密钥有效性
- 检查服务余额
- 确保所选服务正常运行

#### 🌐 代理问题
- 验证代理格式
- 检查代理功能
- 确保代理身份验证正确
