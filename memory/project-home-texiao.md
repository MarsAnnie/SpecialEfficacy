---
name: project-home-texiao
description: home_texiao 项目概述：中盛集团技术十五部案例库首页，融合 Three.js 粒子背景的展示型页面
metadata:
  type: project
---

## 项目定位

中盛集团·技术十五部的部门案例库首页（`index.html`），基于 Three.js 粒子系统做沉浸式背景，叠加玻璃态 UI 内容层。

**Why:** 部门需要一个既展示技术能力又具有实际功能（案例分类、搜索、统计）的首页。

## 核心架构

- **粒子引擎**: Three.js 0.160.0 ES Module + importmap
- **后处理**: EffectComposer + UnrealBloomPass（辉光强度 0.80）
- **粒子着色器**: 自定义 ShaderMaterial（顶点脉冲 + 片元辉光衰减）
- **色彩方案**: 粒子为暖金/琥珀色系（hue 0.04–0.16），UI 文字/强调色为 teal（#00c9a7），形成互补色对比
- **背景星体**: 2800 颗深蓝色星点缓慢旋转

**How to apply:** 修改粒子效果时改 `animate()` 函数中的色相范围；调整辉光改 `bloomBase` 变量或面板滑块。

## 页面结构

1. Hero 区（100vh）：渐变标题 + 搜索栏 + 粒子背景全屏可见
2. 统计栏：4 个计数动画玻璃卡片（128 案例 / 6 领域 / 36 成员 / 99% 满意度）
3. 技术领域：6 分类卡片网格（Web/移动/可视化/集成/UI/AI）
4. 精选案例：3 个案例展示卡（智慧城市 / CloudFlow / VisionGuard）
5. CTA 区 + 页脚

## 设计决策记录

- **粒子色相从 teal 改为暖金**: 原版粒子颜色与 teal 文字/强调色同频，导致视觉层次不清、看久了眼累。改为暖色系后互补对比明显。

## 源文件

- `preview.html` — GPT 生成的粒子 demo（旧版 Three.js r128，有玻璃态 UI）
- `gemini-code-1780540287500.html` — Gemini 生成的粒子 demo（现代架构，Bloom + Shader）
- `index.html` — 融合版本，案例库首页
