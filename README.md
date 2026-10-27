# hue 精裝專輯 — 3D 結構打樣互動模型 (3D Album Structure Interactive Mockup)

> **專案線上展示網址 (Live Demo)**: [https://capelee.github.io/hue-3d/](https://capelee.github.io/hue-3d/)  
> **專案原始碼倉庫 (GitHub Repository)**: [https://github.com/capelee/hue-3d](https://github.com/capelee/hue-3d)

---

## 📖 專案簡介 (Project Overview)

本專案為 **hue 精裝實體專輯** 的次世代 WebGL 3D 互動打樣展示系統。全案採用原生 Three.js 與物理 PBR 材質著色器打造，無額外外部大型引擎依賴，完整呈現實體專輯的微觀印刷工藝、光學折射與立體包裝結構。

---

## ✨ 核心特色與技術規格 (Key Features)

### 1. 壓克力抽拉外盒物理光學 (Acrylic Diamond Bevel & Refractive Sheen)
- **鑽石拋光微倒角高光 (Bevel Chamfer Specular Glints)**：前後板與側邊條邊緣具備 0.68mm ~ 0.72mm 微倒角幾何結構，搭配自訂著色器 96 次方拋光鏡面高光，動態捕捉攝影棚軟光箱亮線。
- **抽拉開盒微透水潤感 (Inner Cavity Translucency)**：啟用雙面物理光學渲染（`side: THREE.DoubleSide`），前後板內壁注入動態菲涅爾微透光膜，抽開時展現 3mm 厚度晶透深度。

### 2. 三變光柵卡與手機體感 (3-Flip Lenticular Card & Tilt Gyroscope)
- **三相光學解密著色器**：真實模擬 125 × 125mm 柱狀透鏡光柵卡，隨視線角度動態切換三階段 RGB 畫面（P1 紅/藍、P2 藍/綠、P3 綠/紅）。
- **手機手持體感連動 (Tilt-to-Lenticular)**：支援 iOS 13+ 與 Android 陀螺儀（`DeviceOrientationEvent`），手持前後或左右傾斜手機即可即時變換光柵圖面，具備**人體工學零點動態校準**與**指數平滑濾波（Lerp Smoothing）**。
- **光柵視角儀 (Lenticular HUD)**：右下角常駐弧形動態儀表指針與即時角度數值顯示。

### 3. 七大多維結構展開模式 (7 Multi-Axis Structural Modes)
1. **01. 標準收合 (Assembled)**：精裝完整收納展示。
2. **02. 抽屜抽出 (Pullout)**：壓克力封套抽開，抽出內層抽屜與歌詞本。
3. **03. 多重翻頁 (Unfold)**：PET 摺頁如蝴蝶翅膀展開，三變光柵卡旋轉亮相。
4. **04. 立體軸向炸裂 (Exploded)**：各組件沿三維空間軸向炸裂，透視內部層次。
5. **05. 水平展開 (Exploded Horizontal)**：橫向一字排開展示。
6. **06. 立體展架 (PET Fold)**：PET 封面直立展示模式。
7. **07. 俯視平鋪 (Knolling)**：全組件以 90 度俯角整齊平鋪陳列，方便整體印刷檢視。

### 4. 頂級打樣工具箱 (Proofing Tools)
- **雙面解密光學比對台 (Optical Dual-Tone Decryption)**：模擬紅藍光濾鏡檢驗歌詞暗碼印刷。
- **多角度棚燈切換 (Studio Lighting Presets)**：純白中性棚、硬光投射、逆光剪影、RGB 印刷三原色單色濾鏡。
- **行動端專屬極簡 UI**：自動適應手機螢幕，隱藏複雜懸浮標籤，底部單一微型 FAB 懸浮鈕點擊即切換視角。

---

## 🚀 本地端運行指南 (Local Development)

本專案採單一自包含 HTML 架構（所有圖像與向量資源均內嵌最佳化），無需複雜打包流程：

1. 克隆倉庫：
   ```bash
   git clone https://github.com/capelee/hue-3d.git
   cd hue-3d
   ```
2. 直接使用任意瀏覽器開啟 `index.html` 或啟動靜態伺服器：
   ```bash
   npx serve .
   # 或使用 Python
   python -m http.server 8080
   ```
3. 在瀏覽器打開 `http://localhost:8080` 即可預覽。

---

## 📱 開啟 GitHub Pages 線上展示步驟

若欲讓他人直接透過網址或手機瀏覽線上展示：
1. 進入 GitHub 倉庫頁面：[https://github.com/capelee/hue-3d](https://github.com/capelee/hue-3d)
2. 點選上方頁籤 **「Settings」** > 左側選單 **「Pages」**。
3. 在 **「Build and deployment」** 下方：
   - **Source**: 選擇 `Deploy from a branch`
   - **Branch**: 選擇 `main`，資料夾選擇 `/ (root)`
4. 點擊 **「Save」**，約 1~2 分鐘後即可透過 `https://capelee.github.io/hue-3d/` 線上瀏覽！
