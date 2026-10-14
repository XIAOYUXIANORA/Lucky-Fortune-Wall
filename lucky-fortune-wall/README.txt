LUCKY FORTUNE WALL — 本地运行说明
=====================================

手势抽牌功能需要摄像头，摄像头又需要 HTTPS 或 localhost 才能工作。
下面是在本地跑的最快方法。

【Mac / Linux】
1. 打开终端
2. cd 到这个文件夹（里面有 index.html）
3. 运行：  python3 -m http.server 8000
4. 浏览器打开：  http://localhost:8000

【Windows】
1. 打开 PowerShell 或 CMD
2. cd 到这个文件夹
3. 运行：  python -m http.server 8000
   （如果没装 Python，去 python.org 装一下）
4. 浏览器打开：  http://localhost:8000

【用法】
- 点 Start → 选 Music → 继续
- 右上角会出现 "Use hands" 按钮
- 点一下，浏览器弹出"允许摄像头"，同意
- 第一次要等几秒下载手部识别模型
- 伸手进摄像头画面，青色光标跟随食指
- 把光标悬停在亮着粉色框的那张卡上 1.5 秒就自动翻开

【不要摄像头的话】
直接点卡牌也能翻，不用开手势。

【注意】
- Chrome / Edge / Safari 都行，Firefox 可能对 MediaPipe 支持差一点
- 第一次开手势需要联网（下载约 10MB 模型）
- 模型会被浏览器缓存，第二次开就秒开
- 光线太暗识别会不准
