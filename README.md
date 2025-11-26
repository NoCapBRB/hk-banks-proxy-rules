# HK Banks Proxy Rules | 香港银行代理规则
![AI Assisted](https://img.shields.io/badge/AI-Assisted-blue)

**非在港用户的香港银行（特别是汇丰）代理规则 / Proxy Rules of HK Banks (especially HSBC HK) for Users outside Hong Kong**

## 简介 / Introduction

本项目旨在为不在香港本地的用户（如中国大陆、海外留学生等）提供针对香港银行 App 的网络分流规则。

主要解决以下痛点：
1.  **HSBC HK Reward+** 等 App 在非香港 IP 下功能受限或无法加载。
2.  普通银行 App（如中银香港、恒生等）在某些网络环境下访问缓慢，但直连通常更稳定。
3.  避免全局代理导致的 IP 乱跳引发风控。

## 规则列表 / Rule Lists

本仓库包含两个主要的规则文件，建议配合使用：

### 1. 汇丰银行规则 (HSBC HK)
* **文件名**: `hsbc_hk.list`
* **建议策略**: 🚀 **PROXY (香港节点)**
* **说明**:
    * **强制走代理**。
    * **原因**: 汇丰香港的 **Reward+ (奖赏钱)** App 有严格的区域限制。如果检测到非香港 IP，App 内的部分页面（如兑换飞行里数、浏览优惠券）会无法加载，甚至无法登录。必须全程使用香港原生 IP 才能解锁所有功能。

### 2. 其他香港银行直连 (HK Banks Direct)
* **文件名**: `hk_banks_direct.list`
* **建议策略**: 🎯 **DIRECT (直连)**
* **说明**:
    * **建议直连**。
    * 收录了除汇丰外的其他常见香港银行（如中银香港、渣打、众安银行等）。
    * 这些银行 App 通常对 IP 宽容度较高，直连访问速度更快且稳定，也能避免因代理节点频繁变动而触发风控。

## ⚠️ 特别说明：美国运通 (American Express)

**本规则库未收录 American Express (Amex) 的规则，原因如下：**

* **域名统一**: 全球的运通网站（无论是美卡还是港卡）大多共用 `americanexpress.com` 这一主域名。
* **难以区分**: 仅通过域名很难精准区分你是要访问 HK 还是 US 站点。
* **处理建议**: 请根据你持有的卡片归属地自行决定策略。
    

## 使用方法 / Usage

应该都会
