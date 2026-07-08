# Cursor 交接说明：巴尔干 11 日自驾地图与行程

请把这个链接发给新电脑上的 Cursor：

https://github.com/ViriShaw/balkan-trip-map/blob/main/CURSOR_HANDOFF.md

## 给新 Cursor 的第一句话

请直接复制下面这段给新电脑上的 Cursor：

```
请接着维护这个巴尔干三国自驾行程网站。

GitHub 仓库：https://github.com/ViriShaw/balkan-trip-map
在线网站：https://virishaw.github.io/balkan-trip-map/
地图页：https://virishaw.github.io/balkan-trip-map/
文字版行程：https://virishaw.github.io/balkan-trip-map/plan.html
交接文件：https://github.com/ViriShaw/balkan-trip-map/blob/main/CURSOR_HANDOFF.md

请先读取仓库里的 index.html、plan.html、plan.md、CURSOR_HANDOFF.md，理解当前行程和网站结构。之后所有行程变更都要同步更新地图页、文字版行程、Markdown 记录和这个交接文件，并推送到 GitHub Pages。
```

## 当前项目状态

这是一个 GitHub Pages 静态网站，用来保存和展示 2026 年 8 月 19 日至 8 月 30 日的巴尔干三国自驾行程。当前版本已从“塞尔维亚 -> 波黑 -> 克罗地亚”改为“塞尔维亚 -> 波黑 -> 黑山 -> 塞尔维亚”的环线。

在线网站：

https://virishaw.github.io/balkan-trip-map/

GitHub 仓库：

https://github.com/ViriShaw/balkan-trip-map

主要文件：

- `index.html`：交互地图页面，手机适配，全屏地图 + 底部行程抽屉。
- `plan.html`：手机可读的文字版完整行程。
- `plan.md`：Markdown 版完整行程，方便 Cursor 和人类继续编辑。
- `CURSOR_HANDOFF.md`：本交接说明。
- `README.md`：仓库简介。

## 当前行程摘要

时间：2026 年 8 月 19 日出发，8 月 30 日回重庆。

人数：3 人。

旅行方式：自驾租车，Airbnb 为主。

路线：塞尔维亚 -> 波黑 -> 黑山 -> 塞尔维亚，贝尔格莱德 BEG 进出。

明确不去：克罗地亚；D3 不含啤酒厂。

交通：重庆 -> 广州中转 -> 贝尔格莱德 BEG；贝尔格莱德取车；贝尔格莱德 BEG 还车；贝尔格莱德 -> 广州中转 -> 重庆。

住宿节奏：

- 8 月 19 日至 8 月 21 日：贝尔格莱德，3 晚。
- 8 月 22 日：乌日策，1 晚。
- 8 月 23 日至 8 月 24 日：萨拉热窝，2 晚。
- 8 月 25 日：莫斯塔尔，1 晚。
- 8 月 26 日至 8 月 27 日：科托尔湾，2 晚。
- 8 月 28 日：扎布利亚克，1 晚。
- 8 月 29 日：贝尔格莱德，1 晚。

逐日路线：

- D1，8 月 19 日：重庆 -> 贝尔格莱德，取车入住，纯路上日。
- D2，8 月 20 日：贝尔格莱德市中心步行。共和国广场、国家博物馆、圣萨瓦大教堂、老城、米哈伊洛大街、卡莱梅格丹、斯卡达里加。
- D3，8 月 21 日：Kosmaj 南线半日。Avala Tower、无名英雄纪念碑、Sopot、Nika 雕塑、Kosmaj 红星纪念碑。
- D4，8 月 22 日：前南建筑线 -> 泽蒙 -> Kadinjaca -> 乌日策。Toblerone Tower、Rudo 东城门、Genex 西城门、Sava Centar、泽蒙、弹孔纪念碑。
- D5，8 月 23 日：乌日策 -> 维舍格勒 -> 萨拉热窝。德里纳河大桥，傍晚到老城。
- D6，8 月 24 日：萨拉热窝全日。Bascarsija、拉丁桥、黄堡，隧道博物馆可选且需打车。
- D7，8 月 25 日：萨拉热窝 -> 莫斯塔尔。Konjic、Jablanica、莫斯塔尔老桥，Blagaj 可选。
- D8，8 月 26 日：莫斯塔尔 -> 科托尔湾。Pocitelj 可选，Trebinje、Herceg Novi、Perast，Kotor 入住。
- D9，8 月 27 日：科托尔湾全日。Kotor Old Town、San Giovanni 城墙、Perast、Our Lady of the Rocks 可选。
- D10，8 月 28 日：科托尔 -> Lovcen -> Cetinje -> Budva 可选 -> Podgorica -> Zabljak。
- D11，8 月 29 日：Durmitor / Black Lake / Tara Bridge -> Zlatibor 可选 -> 贝尔格莱德。
- D12，8 月 30 日：BEG 还车，广州中转飞回重庆。

## 地图实现说明

`index.html` 使用 Leaflet。

底图：

- Carto 完整地名底图。
- OpenStreetMap 备选。
- OSM 德国镜像备选。
- 主要城市中文名以 Leaflet divIcon 叠加显示。

路线：

- 自驾段通过 OSRM 请求实际道路 geometry。
- 步行和本地段使用虚线。
- 每日路线按颜色区分。

标注：

- 每日景点以不同颜色圆形图标显示。
- 三城住宿繁华核心以金色星标显示。
- Airbnb 建议范围以金色虚线圈显示。

手机适配：

- 地图全屏。
- 行程列表是底部抽屉。
- 点击景点后自动收起抽屉并定位。

## 后续维护规则

每次修改行程，都要同步更新这些文件：

- `index.html`：地图数据、路线、点位、住宿标注。
- `plan.html`：手机可读文字版。
- `plan.md`：完整 Markdown 记录。
- `CURSOR_HANDOFF.md`：如果关键行程、链接或维护方式变化，也要更新。

发布方式：

仓库使用 GitHub Pages，从 `main` 分支根目录发布。

更新后访问：

https://virishaw.github.io/balkan-trip-map/

GitHub Pages 有缓存，更新后可能需要等待几十秒到几分钟。

## 仍可继续推进的问题

1. 细化 8 月 20 日至 8 月 23 日的按小时执行版。
2. 给乌日策、莫斯塔尔、科托尔湾、扎布利亚克和最后一晚贝尔格莱德补充具体住宿区域建议。
3. 继续核对塞尔维亚、波黑、黑山三国租车跨境许可、绿卡/保险文件。
4. 复核 D10 科托尔到扎布利亚克路线，Lovcen 和 Budva 视天气和体力取舍。
5. 后续如买到机票，需要把实际航班时间同步进 D1 和 D12。
6. 后续如订好 Airbnb，需要把住宿地址或区域同步到地图。
