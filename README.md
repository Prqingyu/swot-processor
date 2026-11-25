# SWOT 海面高度处理器 · Windows x64 便携版

SWOT 二级产品（SSH / 高度异常）可视处理工具：裁切 NC、生成 PNG 与 GeoTIFF、导出统计结果。
打包为免安装便携版，程序自带 Python 3.12、Qt5、HDF5、netCDF 与全球海岸线，**可完全离线运行**。

## 下载

到 [Releases](../../releases/latest) 页面下载 `SWOT-Processor-Windows-x64.zip`（约 124 MB），
并用同页的 `SHA256.txt` 校验完整性。

## 安装 / 运行

1. 将 ZIP 完整解压到任意目录（路径可含中文与空格）。
2. 保持 `_internal` 文件夹与 `SWOT-Processor.exe` 同级，双击 `SWOT-Processor.exe`。
3. 无需安装 Python、Qt、Conda 或 HDF5，也不需要配置环境变量。

## 使用

- 选择存放 SWOT NC 的输入目录，设置研究区与时间范围，点击「开始处理」。
- 仅预览时输出目录可留空；保存 NC / PNG / TXT / GeoTIFF 时需选择可写目录。
- 「制图标准」中可切换高度异常、水平梯度、归一化与等高线视图；等高距可在弹窗中确认后「保存当前图」。
- 默认海岸线来自 Natural Earth v5.1.2（<https://github.com/nvkelso/natural-earth-vector/tree/v5.1.2/geojson>）。

## 验收范围

本机 Windows x64、隔离路径（含中文与空格）实测通过：清除 Python/Qt/Conda/HDF5 外部环境后启动，
进程加载的 Python 3.12、Qt5Widgets、HDF5、netCDF 均来自解压包；裁切 NC 可回读（23 个变量，
经度数组 683 × 69），PNG / cycle_results.txt / GeoTIFF（600 × 600，EPSG:4326，像元 0.02°，
有效像元 26351）均生成并回读成功，另导出 2934 × 2148 的 PNG 验证通过。
ZIP 完整性与 SHA-256 校验通过。**未**在全新 Windows 虚拟机及全部 NetCDF 压缩插件组合上验收。

## 已知边界

- 仅提供 Windows x64 版本。
- 依赖解压后的目录结构，请勿单独拷走 EXE 运行。
- 第三方组件许可证见压缩包内 `licenses/` 目录。
