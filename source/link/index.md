---
title: 友链
date: 2024-01-06 09:00:00
type: link
---

<!-- ========== 友情链接样式 ========== -->
<style>
  .flink-wrap {
    --flink-radius: 14px;
    --flink-gap: 18px;
    --flink-card-bg: #ffffff;
    --flink-card-border: rgba(0, 0, 0, 0.06);
    --flink-card-shadow: 0 1px 3px rgba(0, 0, 0, 0.04), 0 4px 12px rgba(0, 0, 0, 0.04);
    --flink-hover-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
    --flink-icon-bg: #f7f8fa;
    --flink-text: #1f2328;
    --flink-text-desc: #8b949e;
    --flink-placeholder-color: #c9d1d9;
  }

  /* 深色模式适配（可选，若博客支持 data-theme="dark"） */
  [data-theme="dark"] .flink-wrap,
  .flink-wrap[data-theme="dark"] {
    --flink-card-bg: #1c2128;
    --flink-card-border: rgba(255, 255, 255, 0.08);
    --flink-card-shadow: 0 1px 3px rgba(0, 0, 0, 0.3), 0 4px 12px rgba(0, 0, 0, 0.2);
    --flink-hover-shadow: 0 6px 20px rgba(0, 0, 0, 0.4);
    --flink-icon-bg: #2d333b;
    --flink-text: #e6edf3;
    --flink-text-desc: #8b949e;
    --flink-placeholder-color: #484f58;
  }

  .flink-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: var(--flink-gap);
    margin: 0 0 32px 0;
    padding: 0;
    list-style: none;
  }

  .flink-list-item {
    margin: 0;
  }

  .flink-card {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 16px;
    border-radius: var(--flink-radius);
    background: var(--flink-card-bg);
    border: 1px solid var(--flink-card-border);
    box-shadow: var(--flink-card-shadow);
    text-decoration: none;
    color: var(--flink-text);
    transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
  }

  .flink-card:hover {
    transform: translateY(-3px);
    box-shadow: var(--flink-hover-shadow);
    border-color: rgba(0, 0, 0, 0.1);
  }

  .flink-icon {
    flex-shrink: 0;
    width: 44px;
    height: 44px;
    border-radius: 12px;
    background: var(--flink-icon-bg);
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .flink-icon img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    border-radius: 12px;
  }

  .flink-info {
    min-width: 0;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .flink-name {
    font-size: 15px;
    font-weight: 600;
    line-height: 1.3;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .flink-desc {
    font-size: 13px;
    color: var(--flink-text-desc);
    line-height: 1.3;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  /* 待添加占位卡片 */
  .flink-card.placeholder {
    border: 1.5px dashed var(--flink-placeholder-color);
    background: transparent;
    box-shadow: none;
    cursor: default;
    color: var(--flink-placeholder-color);
    gap: 10px;
  }

  .flink-card.placeholder:hover {
    transform: none;
    box-shadow: none;
    border-color: var(--flink-text-desc);
    color: var(--flink-text-desc);
  }

  .flink-plus {
    width: 44px;
    height: 44px;
    border-radius: 12px;
    background: var(--flink-icon-bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    font-weight: 300;
    line-height: 1;
  }

  .flink-placeholder-text {
    font-size: 14px;
    font-weight: 500;
  }
</style>

<div class="flink-wrap">

  <!-- ========== 实用工具 ========== -->
  <div class="flink-list">
    <div class="flink-list-item">
      <a class="flink-card" href="https://c.runoob.com/" title="菜鸟工具" target="_blank">
        <div class="flink-icon">
          <img src="https://cdn.jsdelivr.net/gh/RK1413686404/ImageShare-X/202401201015956.ico" alt="菜鸟工具" />
        </div>
        <div class="flink-info">
          <div class="flink-name">菜鸟工具</div>
          <div class="flink-desc">开发设计人员工具库</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://catocr.com/" title="CatOCR" target="_blank">
        <div class="flink-icon">
          <img src="https://catocr.com/img/icons/favicon-32x32.png" alt="CatOCR" />
        </div>
        <div class="flink-info">
          <div class="flink-name">CatOCR</div>
          <div class="flink-desc">免费在线图片转文字</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://www.ilovepdf.com/zh-cn/" title="I ❤ PDF" target="_blank">
        <div class="flink-icon">
          <img src="https://www.ilovepdf.com/img/ilovepdf.svg" alt="I ❤ PDF" />
        </div>
        <div class="flink-info">
          <div class="flink-name">I ❤ PDF</div>
          <div class="flink-desc">完全免费的PDF处理工具</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://zhouql.vip/bilibili/" title="B站下载" target="_blank">
        <div class="flink-icon">
          <img src="https://zhouql.vip/bilibili/favicon.ico" alt="B站下载" />
        </div>
        <div class="flink-info">
          <div class="flink-name">B站下载</div>
          <div class="flink-desc">b站视频下载工具</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://wormhole.app/" title="wormhole（虫洞）" target="_blank">
        <div class="flink-icon">
          <img src="https://cdn.jsdelivr.net/gh/RK1413686404/ImageShare-X/202401181648186.webp" alt="wormhole（虫洞）" />
        </div>
        <div class="flink-info">
          <div class="flink-name">wormhole（虫洞）</div>
          <div class="flink-desc">简单私密的文件分享</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="http://iizuka.cs.tsukuba.ac.jp/projects/colorization/web/" title="白黒画像の自動色付" target="_blank">
        <div class="flink-icon">
          <img src="https://media.flaticon.com/dist/min/img/favicon.ico" alt="白黒画像の自動色付" />
        </div>
        <div class="flink-info">
          <div class="flink-name">白黒画像の自動色付</div>
          <div class="flink-desc">AI 自动为黑白图像着色</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://itakeo.github.io/wx/" title="集赞不求人" target="_blank">
        <div class="flink-icon">
          <img src="https://res.wx.qq.com/a/wx_fed/assets/res/OTE0YTAw.png" alt="集赞不求人" />
        </div>
        <div class="flink-info">
          <div class="flink-name">集赞不求人</div>
          <div class="flink-desc">朋友圈集赞200个只需1分钟</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://dazi.91xjr.com/" title="在线打字练习" target="_blank">
        <div class="flink-icon">
          <img src="https://dazi.91xjr.com/static/web/images/favicon.ico" alt="在线打字练习" />
        </div>
        <div class="flink-info">
          <div class="flink-name">在线打字练习</div>
          <div class="flink-desc">摆脱二指禅！</div>
        </div>
      </a>
    </div>
    <div class="flink-list-item">
      <a class="flink-card" href="https://chat.forefront.ai/" title="Forefront AI" target="_blank">
        <div cla