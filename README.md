# ChatGPT 套餐升级差价计算器

一个静态网页工具，用于计算 ChatGPT 套餐升级时的预计补款金额。

## 使用方式

部署后直接访问 `index.html`。选择当前套餐、目标套餐及当前套餐的剩余天数，页面会实时显示旧套餐剩余价值、抵扣金额和预计补款。

计算公式：

```text
预计补款 = max(0, 目标套餐价格 - 当前套餐价格 × 剩余天数 ÷ 计费周期天数)
```

两个天数输入框仅按整数天数计算。

## 配置

页面启动时读取 [`static/config.json`](static/config.json)。可直接修改此文件来更新套餐价格和客服联系信息，无需改动 `index.html`。

```json
{
  "prices": {
    "plus": 130,
    "x5": 720,
    "x20": 1180
  },
  "contact": {
    "label": "联系客服",
    "hint": "扫码添加微信客服",
    "imagePath": "static/wechat.JPG",
    "imageAlt": "微信客服二维码",
    "wechatId": "lllulitao"
  }
}
```

| 字段 | 作用 |
| --- | --- |
| `prices.plus` | Plus 月价 |
| `prices.x5` | Pro x5 月价 |
| `prices.x20` | Pro x20 月价 |
| `contact.label` | 标题右侧客服按钮文案 |
| `contact.hint` | 二维码上方提示文案 |
| `contact.imagePath` | 客服二维码图片的相对路径或 URL |
| `contact.imageAlt` | 二维码图片的替代文本 |
| `contact.wechatId` | 可点击复制的微信号 |

## 客服入口

标题右侧的“联系客服”按钮支持鼠标悬停或点击展开。卡片中展示二维码和微信号；点击微信号可复制到剪贴板。

## 搜索关键词

ChatGPT 套餐升级差价计算器、ChatGPT 升级补款、ChatGPT Plus 代充、ChatGPT Pro 代充、菲区代充、菲区 ChatGPT Plus、菲区 ChatGPT Pro、ChatGPT Plus 升级 Pro、ChatGPT Pro x5、ChatGPT Pro x20、ChatGPT 订阅充值、ChatGPT 套餐价格。

## 目录结构

```text
.
├── index.html          # 页面与计算逻辑
├── README.md           # 使用与配置说明
└── static/
    ├── config.json     # 价格和客服联系配置
    └── wechat.JPG      # 默认微信客服二维码
```
