# AOSP Note

该仓库主要是我个人在 Android 系统开发中整理的文档，主要由 **note** 、**docs**、**articles** 构成。**note** 是对 AOSP 在源码级别的注释，因此目录结构与 AOSP 保持一致。**docs** 相当于是为 AOSP 写的设计文档，主要包括模块架构图、模块工作流程、工作原理的分析，也有对 AOSP 一些基础库做的源码分析。**articles** 是一些根据某一主题撰写的独立的文章，包括技术原理剖析，结合具体场景的源码分析以及问题分析经验。

所有文档使用 Markdown 写成，使用 drawio 绘图，然后导出为 SVG 图片插入文档。drawio 源文件和图片同一放在 pic 目录下，引用图片时使用相对路径。目前文档主要是在阅读 Android 12 的源码写出，考虑到 Android 每个大版本的源码有些差异，所以仓库分别建立了分支进行维护，每一 Android 大版本对应一个分支，对于不同版本有差异的地方，文档会做标注，此时可以切换到对应分支，阅读对应的文档。

目前文档以 Android 图形(Graphic)模块为主，会涉及 Android 系统基础机制(技术) 包括 HAL，MessageQueue，Binder 等



articles 目前已完成的文章

- [ ] Android GUI 系统概述
- [ ] Android 文本渲染





