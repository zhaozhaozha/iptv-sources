# IPTV-Sources · 影视仓 / TVBox 直播源

> **765 个直播频道**，以 vbskycn 公共源为底子，叠加虎牙「一起看」电影 / 电视剧轮播频道合并而成。
> 已在 2026-10 完成全量去重 + 真流校验（无 13 位 uid 假房间、无 2:14 广告占位片）。

A Chinese IPTV playlist (765 channels) for **TVBox / 影视仓(YSC) / Kodi / VLC / PotPlayer**.
Curated & verified: deduplicated, real-stream checked, ready to import by URL.

---

## 📡 直播源地址

### 通用版（推荐 · 影视仓 / TVBox / Kodi / PotPlayer）

```
https://cdn.jsdelivr.net/gh/zhaozhaozha/iptv-sources@main/vbsky-huya.m3u
```

### VLC 专用版（含 `#EXTVLCOPT` 请求头指令）

```
https://cdn.jsdelivr.net/gh/zhaozhaozha/iptv-sources@main/vbsky-huya-vlc.m3u
```

<details>
<summary>备用地址（jsDelivr 被墙时使用）</summary>

```
https://raw.githubusercontent.com/zhaozhaozha/iptv-sources/main/vbsky-huya.m3u
https://raw.githubusercontent.com/zhaozhaozha/iptv-sources/main/vbsky-huya-vlc.m3u
```

</details>

---

## 🗂 频道内容总览（765 台 / 12 个分组）

| 分组 | 台数 | 内容类型 |
| :--- | ---: | :--- |
| **央视频道** | 32 | CCTV1–17 全系列、CCTV5+、CCTV6 电影、CGTN 等 |
| **卫视频道** | 44 | 全国省级卫视（东方 / 湖南 / 江苏 / 浙江 / 北京 / 广东…） |
| **地方频道** | 250 | 全国各地市台、县台、新闻综合、公共频道（含量最大） |
| **虎牙频道** | 191 | 🎬 虎牙「一起看」电影直播间：星爷 / 英叔 / 成龙 / 发哥 / 漫威 / 港片 / 战争 / 喜剧 / 玄幻… |
| **轮播剧场** | 140 | 📺 24 小时剧集轮播：港剧、TVB 西游记、雍正王朝、神探狄仁杰、新三国、僵尸片、经典电影… |
| **电影频道** | 38 | CHC 系列（CHC 电影 / CHC 动作电影）、影视娱乐台、经典喜剧轮播 |
| **纪录频道** | 30 | CGTN 纪录、航拍中国、人与自然、地方纪录频道 |
| **春晚频道** | 22 | 1987–近年央视春晚全场回放（怀旧向） |
| **儿童频道** | 9 | 卡酷少儿、金鹰卡通、动漫秀场、猫和老鼠、中华小当家 |
| **音乐频道** | 4 | 风云音乐、AMC 音乐、音乐现场 |
| **体育频道** | 3 | 广东体育、纬来体育、精品体育 |
| **数字频道** | 2 | 南国都市、四川科教 |

**内容覆盖一句话**：央视 + 卫视 + 地方台（日常看电视）+ 虎牙电影直播间 + 剧集轮播剧场（追剧 / 看片主力）。

---

## ✅ 兼容应用

| 应用 | 使用版本 | 说明 |
| :--- | :--- | :--- |
| **影视仓 (YSC)** | 通用版 | 支持粘贴 **TXT / M3U 两种 URL**，直接填上方地址即可 |
| **TVBox / 猫影视 / 月光宝盒** | 通用版 | 作为「直播源 / 订阅」URL 导入 |
| **Kodi** (PVR IPTV Simple Client) | 通用版 | M3U 播放列表 URL 直接填 |
| **VLC** | **VLC 专用版** | 需请求头才能播虎牙源，见下方说明 |
| **PotPlayer / nPlayer / MX Player** | 通用版 | 打开网络串流 / 导入 URL |
| **OPlayer / 我播 / 电视家类** | 通用版 | 按「自定义直播源」导入 |

---

## 🎯 两个文件怎么选

| | `vbsky-huya.m3u` | `vbsky-huya-vlc.m3u` |
| :--- | :--- | :--- |
| 台数 | 765 | 765（完全相同） |
| 体积 | 约 150 KB | 约 300 KB |
| `#EXTVLCOPT` | ❌ 无 | ✅ 1880 条 |
| 适用 | 影视仓、TVBox、Kodi、手机播放器 | **VLC 桌面版** |
| 原因 | 播放器自带 UA 处理 | VLC 不会自动带 User-Agent / Referer，虎牙源会 403 |

VLC 版每个频道预置了：
- `http-user-agent`（765 台全带）
- `network-caching=1000`（765 台全带，降低卡顿）
- `http-referrer`（350 台带，虎牙及部分地方台必需）

> ⚠️ 用 VLC 请务必选 **VLC 专用版**，否则虎牙频道全部播不了。

---

## 🚀 快速使用

### 影视仓 (YSC) / TVBox

1. 复制通用版地址：
   `https://cdn.jsdelivr.net/gh/zhaozhaozha/iptv-sources@main/vbsky-huya.m3u`
2. 进入 **设置 → 直播 / 自定义直播源 → 添加**
3. 粘贴地址保存 → 刷新 → 频道列表出现 12 个分组、765 个台

### VLC

1. 下载 [VLC](https://www.videolan.org/vlc/)
2. `媒体` → `打开网络串流` → 粘贴 VLC 专用版地址 → 播放
   （或保存为 `.m3u` 本地文件后直接拖入 VLC 窗口）
3. 左侧播放列表按分组浏览，双击换台

---

## 🔧 数据说明

- **来源构成**：vbskycn 公共 IPTV 源为主干（央视 / 卫视 / 地方 / 纪录 / 儿童 / 音乐 / 体育），叠加虎牙「一起看」影视直播间（`虎牙频道` + `轮播剧场`）。
- **协议分布**：`https` 488 台 / `http` 277 台。
- **质量校验**：虎牙系列全部改用 `profileRoom`（8 位真房间号）取流，响应首字节必须为 `FLV` —— 已剔除所有返回 2:14 广告占位片的失效频道。
- **去重策略**：全表同名频道保留 **虎牙频道** 分组版本，重复 0 条。
- **CDN**：走 jsDelivr 全球加速；更新后如未生效可访问 `https://purge.jsdelivr.net/gh/zhaozhaozha/iptv-sources@main/vbsky-huya.m3u` 刷新缓存。

---

## 🩺 播放异常排查

| 现象 | 原因 | 处理 |
| :--- | :--- | :--- |
| 虎牙频道播成 2:14 短片 | 用的是失效房间号 | 拉取最新版列表 |
| 频道打不开 / 一直转圈 | 源站临时限流或已下线 | 换同分组其他台，或等下次刷新 |
| VLC 里全部不了 | 用了通用版 | 换 `vbsky-huya-vlc.m3u` |
| 影视仓里部分台黑屏 | 部分地方台仅限本地网络 | 属源本身限制，非列表问题 |
| jsDelivr 拉取失败 | CDN 节点问题 | 改用上方 raw 备用地址 |

---

## 📌 维护

- 虎牙「一起看」直播间会不定期换房间号，轮播台开播率下降时需重新抓取并刷新列表。
- 列表持续可用期约数周，建议长期使用时定期重新拉取。
- 欢迎 Issue 反馈失效频道。

---

## ⚠️ 免责声明

本项目仅收集整理互联网公开的 IPTV 直播流地址，**不存储、不转码、不分发任何音视频内容**，所有流的版权归原始权利方所有。
仅供个人学习与技术研究使用，请于下载后 24 小时内删除。因使用本列表产生的一切后果由使用者自行承担。

---

_Last updated: 2026-10-05 · 765 channels · 12 groups_
