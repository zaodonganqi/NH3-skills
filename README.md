# NH3.skill

**简体中文** | [English](docs/README.en.md)

NH3.skill 是一个个人维护、可跨项目复用的多框架前端 Skill。它不属于任何业务项目，也不包含私有项目源码、目录、路由、资源、配置或业务命名。

NH3 提供两种相互隔离的能力：

- `frontend-engineering`：多框架前端工程、应用架构、重构、操作型 UI、环境、安全、验证和发布准备。
- `reference-site-design`：从参考中抽象视觉、布局、动效和交互系统，用于公共营销、发布、活动和产品网站。

只有显式选择 `combined` 时才会同时启用两种模式，避免把后台工程规则套到营销网站，或把活动型视觉规则混入操作型应用。

## 目录

- [内容](#内容)
- [模式与使用](#模式与使用)
- [框架范围](#框架范围)
- [代码格式](#代码格式)
- [保密边界](#保密边界)
- [维护](#维护)
- [许可证](#许可证)

## 内容

```text
NH3-skills/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── zh-CN.md
│   ├── frontend-engineering.md
│   ├── framework-adapters.md
│   ├── code-style.md
│   └── reference-design/
│       ├── mode.md
│       ├── system.md
│       ├── motion.md
│       └── review.md
├── docs/
│   └── README.en.md
├── .editorconfig
├── LICENSE
└── README.md
```

## 模式与使用

将本目录复制或安装到支持 Skill 的 AI 编码工具所使用的位置。调用时明确指定模式。

工程模式：

```text
Use $nh3 in frontend-engineering mode to review this React dashboard and fix the issues you find.
```

参考设计模式：

```text
Use $nh3 in reference-site-design mode to redesign this public product site from the supplied references.
```

明确需要两者时：

```text
Use $nh3 in combined mode for this full-stack framework's public product surface.
```

未指定模式且页面性质存在歧义时，Skill 会要求调用者选择，不会自行混用。

## 框架范围

NH3 适用于浏览器前端和全栈框架的前端表面，包括但不限于：

- React、Next、Remix 类技术栈；
- Vue、Nuxt；
- Svelte、SvelteKit；
- Angular；
- Solid、SolidStart；
- Astro 及多框架 islands；
- 原生 HTML、CSS、JavaScript、TypeScript 和类似 Web 工具链。

Skill 先识别目标仓库的框架、路由、渲染模式、状态、样式、测试和部署边界，再映射通用职责。不会把 Vue、React 或任何真实项目的目录结构复制到其他框架。

纯后端、纯基础设施、原生 Android/iOS、桌面原生应用和无关数据管道不在范围内。

## 代码格式

仓库既有 formatter、lint 和 EditorConfig 优先。无本地规则时使用：

- UTF-8；
- LF 换行；
- 文件末尾保留一个换行；
- 代码和配置不保留行尾空格；
- 常见 Web 格式使用两个空格缩进；
- 手写代码采用 100 列软限制；
- 长结构按参数、属性或 props 的语义边界折行；
- 不格式化生成代码、lockfile、snapshot 或无关文件。

完整规则见 [references/code-style.md](references/code-style.md)。

## 保密边界

此仓库只允许保存可移植的前端原则、职责边界、判断标准和中性示例。

禁止写入或对外传播：

- 私有项目源码；
- 真实项目目录树和模块命名；
- 内部路由、业务文案、角色和权限名称；
- 品牌资源、截图、配置值和基础设施信息；
- 从单个项目直接复制的组件、样式或交互实现。

真实项目只能用于提炼框架级关系，必须移除所有可识别实现细节。

## 维护

保持 `SKILL.md` 作为精简的模式路由和共享基线。详细规则放在对应 references 中，避免两种模式直接融合。

`references/zh-CN.md` 是 `SKILL.md` 的中文对照；新增框架规则应进入 `framework-adapters.md`，新增工程规则进入 `frontend-engineering.md`，参考驱动设计规则保持在 `reference-design/` 内。

所有文本使用 UTF-8 和 LF。修改后运行 Skill 校验、Markdown 引用检查、`git diff --check` 和私有信息扫描。

## 许可证

Apache-2.0
