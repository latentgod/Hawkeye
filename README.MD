# Hawkeye

[![GitHub issues](https://img.shields.io/github/issues/0xbug/Hawkeye.svg)](https://github.com/0xbug/Hawkeye/issues)
[![GitHub forks](https://img.shields.io/github/forks/0xbug/Hawkeye.svg)](https://github.com/0xbug/Hawkeye/network)
[![GitHub stars](https://img.shields.io/github/stars/0xbug/Hawkeye.svg)](https://github.com/0xbug/Hawkeye/stargazers)
[![Python 3.x](https://img.shields.io/badge/python-3.x-yellow.svg)](https://www.python.org/) 
[![GitHub license](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://raw.githubusercontent.com/0xbug/Hawkeye/master/LICENSE)

## 简介

> 监控github代码库，及时发现员工托管公司代码到GitHub行为并预警，降低代码泄露风险。

## 特性

- 邮箱告警通知
- 黑名单添加
- 爬虫任务设置

## 依赖

*   Python 3.x
*   Flask
*   MongoDB

## 支持平台

*   Linux, macOS


## 安装

克隆项目到本地

```
git clone https://github.com/0xbug/Hawkeye.git --depth 1
```


Hawkeye 支持 Python *3.x* on Linux and macOS。(2.x兼容性 需自行修改测试)

安装依赖

```
cd Hawkeye
virtualenv --python=/usr/local/bin/python3 venv
source venv/bin/activate
pip install -r deploy/requirements.txt

```


## 设置

```bash
cp config.ini.example config.ini
vim config.ini
```

### 需要修改的配置

- `github` 帐户配置
```
[GitHub]
USERNAME = 帐号
PASSWORD = 密码
```

- 告警配置（`ENABLE`:是否开启告警功能）

```
[Notice]
ENABLE = 1
MAIL_SERVER = 邮件服务器
FROM = 发件人
PASSWORD = 密码
```

## 运行

```bash
python Hawkeye.py
```
然后访问 http://0.0.0.0:5000/ 进行关键词、告警、黑名单、定时任务配置。

## 部署

建议使用 `supervisor` 设置成开机自启，并监控进程，配置文件 `deploy/Hawkeye.conf.example`