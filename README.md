# TimePortal V0.3 — 真正去背傳輸版

本版修正上一版「整個手機矩形畫面疊到老照片」的錯誤。

## 正確流程

手機：
1. 相機取得真人影像
2. MediaPipe 產生人物遮罩
3. 手機裁出人物
4. 手機把「綠幕＋人物」Canvas 傳到電腦

電腦：
1. 收到綠幕人物影片
2. WebGL 即時去除綠色
3. 只把人物疊到 background.jpg

## 為什麼不是直接傳透明人物？

一般 WebRTC 視訊編碼不可靠保留 Alpha 透明通道，因此本原型使用綠幕傳輸，再由電腦端 GPU Shader 去綠。

## 使用

把下列檔案全部覆蓋到 GitHub Pages：
- index.html
- style.css
- script.js
- background.jpg

測試流程：
1. 電腦開唯一網址
2. 按「在這台電腦開啟大螢幕」
3. 手機掃 QR Code
4. 手機按「開啟相機並連線」
