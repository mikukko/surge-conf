# surge-conf

Surge 配置 & 自动签到模块，支持 NGA、V2EX、IT之家 三个站点的每日自动签到。

## 签到模块

### 安装

在 Surge 中安装模块：

```
https://raw.githubusercontent.com/mikukko/surge-conf/master/module/sign.sgmodule
```

### 使用方式

1. 安装模块后，打开 **MITM** 并信任证书
2. 分别打开对应 App/网站触发 Cookie 获取：
   - **NGA** — 打开 NGA App，进入"刮墙"页面
   - **V2EX** — 浏览器访问 `https://www.v2ex.com/mission/daily`
   - **IT之家** — 打开 IT之家 App，进入签到页面
3. 收到通知提示 Cookie 获取成功即可
4. 每日 0:10 自动执行签到任务

### 签到站点

| 站点 | Cookie 获取 | 每日签到 |
|------|------------|---------|
| NGA  | `nga_cookie.js` | `nga.js` — 刮墙 + 领取任务奖励 |
| V2EX | `v2ex_cookie.js` | `v2ex.js` — 领取每日登录奖励 |
| IT之家 | `ithome_cookie.js` | `ithome.js` — 签到 + 查询连续签到信息 |

## 目录结构

```
├── surge.conf              # Surge 主配置
├── module/
│   └── sign.sgmodule       # 自动签到模块
└── scripts/
    ├── nga_cookie.js       # NGA Cookie 获取
    ├── nga.js              # NGA 每日签到
    ├── v2ex_cookie.js      # V2EX Cookie 获取
    ├── v2ex.js             # V2EX 每日签到
    ├── ithome_cookie.js    # IT之家 Cookie 获取
    └── ithome.js           # IT之家 每日签到
```

## MITM 域名

- `ngabbs.com`
- `www.v2ex.com`
- `napi.ithome.com`
