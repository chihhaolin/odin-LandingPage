# 設計規範（參考 The Odin Project 原始規範）

---

## 字型
- 全站使用：**Roboto**（Google Fonts）

---

## 色彩系統

| 用途 | 色碼 |
|------|------|
| Hero 背景色、Footer 背景色 | `#1F2937` |
| Hero 主標題文字色、Logo 文字色 | `#F9FAF8` |
| Hero 副標題文字色、Header 導覽連結 | `#E5E7EB` |
| 按鈕背景色、CTA 區背景色 | `#3882F6` |
| Quote 區背景色 | `#E5E7EB` |
| 一般內文、標題（白底區段） | `#1F2937` |

---

## 字型樣式

| 用途 | 大小 | 粗細 |
|------|------|------|
| Hero 主標題 | 48px | 900（Black） |
| Hero 副標題 / 導覽連結 | 18px | 400（Regular） |
| Logo 文字 | 24px | 700（Bold） |
| 特色區標題（Section Header） | 36px | 900（Black） |
| 引言文字（Quote） | 36px | 300（Light），斜體 |

---

## 版面結構（Flexbox 為主）

### Header
- 左：Logo 文字
- 右：導覽連結（橫排，間距均等）
- 背景色：`#1F2937`

### Hero
- 左：主標題 + 副標題 + CTA 按鈕（垂直排列）
- 右：圖片（圓角）
- 背景色：`#1F2937`
- 整體：水平 Flexbox，垂直置中

### 特色介紹區
- 上：Section 標題（置中）
- 下：4 張 Card 橫排（Flexbox，justify: space-evenly）
- 每張 Card：圖片（圓角邊框）+ 說明文字（置中）
- 背景色：白色 `#FFFFFF`

### Quote 區
- 引言文字（置中，斜體）
- 署名（靠右）
- 背景色：`#E5E7EB`

### CTA 區
- 左：標題 + 說明文字
- 右：按鈕（圓角邊框，白色文字，藍色背景）
- 背景色：`#3882F6`
- 整體：水平 Flexbox，垂直置中

### Footer
- 版權文字（置中）
- 背景色：`#1F2937`，文字色：`#E5E7EB`