# 素材、科学参考与授权

## 月球

- NASA Scientific Visualization Studio — **CGI Moon Kit**: https://svs.gsfc.nasa.gov/4720/
- 原图：`lroc_color_poles_4k.tif`，4096×2048。
- 高程：`ldem_16_uint.tif`，5760×2880，LRO/LOLA，16 位半米单位，偏移 +10 km，基准半径 1737.4 km。
- 本包颜色图压缩为 JPEG；高程无损拆入 PNG 的 R/G 通道，已逐像素验证可还原原始整数值。
- 署名：NASA's Scientific Visualization Studio / LRO / LROC / LOLA；Ernie Wright。

## 水星、火星、地球、木星、土星、天王星、海王星、太阳与环带

- 来源与下载：**Solar System Scope / INOVE** — https://www.solarsystemscope.com/textures/
- 授权：**Creative Commons Attribution 4.0 International (CC BY 4.0)** — https://creativecommons.org/licenses/by/4.0/
- 素材名：`8k_mercury.jpg`, `8k_mars.jpg`, `8k_jupiter.jpg`, `8k_earth_daymap.jpg`, `2k_saturn.jpg`, `2k_saturn_ring_alpha.png`, `2k_uranus.jpg`, `2k_neptune.jpg`, `2k_earth_nightmap.jpg`, `2k_earth_clouds.jpg`, `2k_earth_specular_map.tif`, `2k_sun.jpg`。
- 原作者说明这些图像基于 NASA 高程及影像，参考 MESSENGER、Viking、Cassini、Hubble 与 Blue Marble。原作者明确说明部分缺测区域有虚构补绘，颜色也有增强。
- 0.5.0 高清包：水星、金星雷达地表、火星、地球白昼／夜景／云图保留原始 8192×4096 JPEG 字节，不缩小、不再编码；木星、土星与太阳下载地址虽标为 8k，实际原图为 4096×2048，按实测尺寸提供。天王星与海王星来源仅提供 2048×1024，本版不虚构纹理或将放大当作新增细节；海王星保留此前的浅蓝青色重平衡。
- App 中建议保留：**Planet textures: Solar System Scope / INOVE, based on NASA data, CC BY 4.0. Resized and color-adjusted.** 并附上方来源及授权链接。

## 冥王星

- NASA / Johns Hopkins University Applied Physics Laboratory / Southwest Research Institute。
- **Pluto Global Color Map**, New Horizons Ralph MVIC, 2017-01-20。比早期 PIA19956 提供更完整的全球颜色覆盖；远侧分辨率较低。
- 来源：https://science.nasa.gov/resource/pluto-global-color-map/
- JPEG 原图：https://assets.science.nasa.gov/content/dam/science/psd/solar/2023/09/p/l/pluto_color_mapmosaic.jpg
- 0.5.0 恢复 NASA 原始 5926×2963 JPEG 字节；不再缩小或填充缺测区，关闭程序生成的地貌补绘。保留实测拼接图的缺测与原始分辨率差异。此图为增强色，并非自然色或完整的同分辨率全球测绘。

## 科学与视觉参考

- 直径、自转与轴倾角：NASA **Planetary Fact Sheet**, 2025-03-18 版：https://nssdc.gsfc.nasa.gov/planetary/factsheet/
- 月球同步自转：https://science.nasa.gov/moon/moon-phases/
- 太阳赤道约 25 天自转、极区更慢：https://science.nasa.gov/sun/facts/
- Neptune/Uranus 近自然色研究方向：University of Oxford, 2024-01-05：https://www.ox.ac.uk/news/2024-01-05-new-images-reveal-what-neptune-and-uranus-really-look-0
- 黑洞吸积盘透镜与多普勒亮度参考：NASA Goddard / Jeremy Schnittman, **Black Hole Accretion Disk Visualization**：https://svs.gsfc.nasa.gov/13326/
- 黑洞图像由本包程序生成，没有复制 NASA 影片或音乐。

## 自编代码

MIT License

Copyright (c) 2026 Celestial Kit contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

This code license does not replace the separate licenses and attribution requirements of third-party textures.

## 0.5.0 GPU 与资源验证

高分辨率图片以原始像素分片上传至 WebGL 2 纹理数组，在 GPU 最大单张纹理尺寸为 4096 时也不缩图。手动双线性采样跨越分片边界，保持经度回绕及纬度钳制。渲染清晰度上限提高，仍受屏幕及 GPU 绘制缓冲尺寸限制。黑洞仍为引力透镜近似可视化，不是任何特定黑洞的实拍。

- `mercury.jpg`: 8192×4096, SHA-256 `5c8bd885ae3571c6ba2cd34b3446b9c6d767e314bf0ee8c1d5c147cadd388fc3`; https://www.solarsystemscope.com/textures/download/8k_mercury.jpg
- `venus-surface.jpg`: 8192×4096, SHA-256 `9bc21a50577ed8ac734cda91058724c7a741c19427aa276224ce349351432c5b`; https://www.solarsystemscope.com/textures/download/8k_venus_surface.jpg
- `mars.jpg`: 8192×4096, SHA-256 `4cc52149924abc6ae507d63032f994e1d42a55cb82c09e002d1a567ff66c23ee`; https://www.solarsystemscope.com/textures/download/8k_mars.jpg
- `earth.jpg`: 8192×4096, SHA-256 `88ab060b6e7d241cfc590c69f528fab2b3247b738d40124cb590999a6fe44abc`; https://www.solarsystemscope.com/textures/download/8k_earth_daymap.jpg
- `clouds.jpg`: 8192×4096, SHA-256 `c792eca228989d36ebb45d3ea6ff1198be5e21a25d70d2fbcb2124ffd14ba7f5`; https://www.solarsystemscope.com/textures/download/8k_earth_clouds.jpg
- `night.jpg`: 8192×4096, SHA-256 `9894e83a585a22c1c425e7ca4f987a9ba625bf08ecee45d3c9dcacae3c2ad5f7`; https://www.solarsystemscope.com/textures/download/8k_earth_nightmap.jpg
- `jupiter.jpg`: 4096×2048, SHA-256 `0bd844bf20822c4e3e80882b077859833c0dac44c7e4e1e0cd63d1b1b6d43085`; https://www.solarsystemscope.com/textures/download/8k_jupiter.jpg
- `saturn.jpg`: 4096×2048, SHA-256 `0d39a4a490c87c3edabe00a3881a29bb3418364178c79c534fe0986e97e09853`; https://www.solarsystemscope.com/textures/download/8k_saturn.jpg
- `sun.jpg`: 4096×2048, SHA-256 `f22b1cfb306ddce72a7e3b628668a0175b745038ce6268557cb2f7f1bdf98b9d`; https://www.solarsystemscope.com/textures/download/8k_sun.jpg
- `pluto.jpg`: 5926×2963, SHA-256 `d63da5ee9eab8d0b98ebef3c0cdc3a92676d7c9b247b2383294fb5da5c67a71a`; https://assets.science.nasa.gov/content/dam/science/psd/solar/2023/09/p/l/pluto_color_mapmosaic.jpg
