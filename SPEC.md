# City Weather Map - 城市天气地图

## 1. Project Overview

- **Project name**: City Weather Map
- **Project type**: Single-page interactive website
- **Core functionality**: 在交互式地图上显示上海、维也纳、慕尼黑三个城市的位置，并展示各地实时时间、天气和穿衣提示
- **Target users**: 需要了解多城市天气信息的旅行者或商务人士

## 2. UI/UX Specification

### Layout Structure

- **全屏地图**：使用 Leaflet.js 交互式地图（OpenStreetMap）
- **信息卡片**：三个城市的信息卡片悬浮在地图上
- **响应式**：桌面端横向排列，移动端纵向堆叠

### Visual Design

- **Color Palette**:
  - 主色：#1a1a2e（深蓝黑）
  - 强调色：#e94560（珊瑚红）
  - 背景：#16213e（深蓝）
  - 卡片背景：rgba(22, 33, 62, 0.95)
  - 文字：#eaeaea
  - 城市标记颜色：
    - 上海：#e94560（珊瑚红）
    - 维也纳：#ffd700（金色）
    - 慕尼黑：#00d9ff（青色）

- **Typography**:
  - 标题：Noto Sans SC, 18px, font-weight: 700
  - 正文：Noto Sans SC, 14px
  - 时间：JetBrains Mono, 32px, font-weight: 700

- **Spacing**:
  - 卡片内边距：20px
  - 卡片圆角：16px
  - 元素间距：12px

- **Visual Effects**:
  - 卡片：毛玻璃效果 (backdrop-filter: blur(10px))
  - 卡片阴影：0 8px 32px rgba(0, 0, 0, 0.3)
  - 城市标记：脉冲动画效果
  - 卡片悬停：轻微上浮和发光效果

### Components

1. **地图容器**
   - 全屏 Leaflet 地图
   - 深色地图主题（Cartodb Dark Matter）

2. **城市信息卡片**
   - 城市名称（中英文）
   - 当前时间（实时更新）
   - 天气图标和描述
   - 温度
   - 穿衣建议

3. **地图标记**
   - 自定义彩色标记
   - 脉冲动画
   - 点击弹出详情

## 3. Functionality Specification

### Core Features

1. **地图显示**
   - 初始视野包含三个城市
   - 可拖拽、缩放
   - 城市标记可点击

2. **实时时钟**
   - 每秒更新
   - 显示各地本地时间

3. **天气信息**（使用免费 API）
   - 使用 Open-Meteo API（免费无需 API key）
   - 获取当前天气数据

4. **穿衣建议**
   - 根据温度自动生成建议
   - <10°C：冬季外套
   - 10-20°C：薄外套或长袖
   - 20-25°C：长袖
   - >25°C：短袖

### Data Handling

- 城市坐标：
  - 上海：31.2304, 121.4737
  - 维也纳：48.2082, 16.3738
  - 慕尼黑：48.1351, 11.5820

- API：https://api.open-meteo.com/v1/forecast

## 4. Acceptance Criteria

- [ ] 地图正确显示三个城市位置
- [ ] 三个城市时间实时更新
- [ ] 天气数据正确获取显示
- [ ] 穿衣建议根据温度显示
- [ ] 卡片样式美观，有动画效果
- [ ] 移动端正常显示