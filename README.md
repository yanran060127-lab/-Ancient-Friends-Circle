# 古人朋友圈 · Ancient Friends Circle

> 基于 Dify 平台与 DeepSeek 大模型构建的历史人物角色扮演 AI 智能体

一个让用户与历史人物"跨时空对话"的 LLM 应用。通过结构化输入(身份 / 朝代 / 核心价值观),智能体会以对应历史人物的人格、语气与价值观与用户进行对话,适用于历史教育、文化普及与角色扮演娱乐场景。

---

## 🌟 项目亮点

- **零代码工作流编排**:基于 Dify 可视化平台搭建,实现复杂多分支对话逻辑
- **人格化差异回复**:通过条件路由设计,不同价值观的历史人物呈现差异化语言风格
- **国产大模型集成**:接入 DeepSeek-Chat,响应速度快、中文表现优异
- **可一键复现**:提供完整 DSL 配置文件,导入 Dify 即可运行

---

## 🛠️ 技术栈

| 模块 | 技术 |
| --- | --- |
| 应用平台 | [Dify](https://dify.ai/) |
| 大语言模型 | DeepSeek-Chat |
| 工作流类型 | Chatflow(对话型工作流) |
| 核心节点 | 用户输入 · 条件分支 · LLM 调用 · 直接回复 |

---

## 🧩 工作流架构

![工作流架构图](screenshots/workflow.png)

整体流程:

1. **用户输入节点**:接收三个必填变量
   - `identity`:历史人物身份(如"诗人""谋士""帝王")
   - `era`:所处朝代(如"唐""三国""明")
   - `core_value`:核心价值观(如"入世向学""出世归隐")

2. **条件分支节点**:根据 `core_value` 字段判断走向
   - **IF 分支**:若包含"入世向学",路由至积极入世型人格 LLM
   - **ELSE 分支**:路由至超脱出世型人格 LLM

3. **LLM 调用节点**:DeepSeek-Chat 基于角色 Prompt 生成回复

4. **直接回复节点**:将生成内容返回给用户

---

## 🚀 快速开始

### 方式一:导入 DSL 到 Dify(推荐)

1. 注册 / 登录 [Dify 云端版](https://dify.ai/)
2. 在工作室中点击「创建应用」→「导入 DSL 文件」
3. 上传本仓库中的 `古人朋友圈.yml`
4. 配置你自己的 DeepSeek API Key
5. 点击「发布」即可使用

### 方式二:本地部署 Dify

如需本地部署,可参考 [Dify 官方文档](https://docs.dify.ai/getting-started/install-self-hosted)。

---

## 💡 使用示例

**输入:**
- identity: 诗人
- era: 唐
- core_value: 入世向学

**预期输出风格:** 模拟杜甫、李白等积极入世诗人的口吻,讨论功业、家国与求学之志。

**输入:**
- identity: 隐士
- era: 魏晋
- core_value: 出世归隐

**预期输出风格:** 模拟陶渊明、嵇康等隐逸文人的口吻,谈论山林之乐与道家哲思。

---

## 📁 仓库结构

```
ancient-friends-circle/
├── README.md              # 项目说明文档
├── dify_workflow.yml      # Dify 工作流 DSL 配置
└── screenshots/
    └── workflow.png       # 工作流架构截图
```

---

## 🔮 后续优化方向

- [ ] 接入 Dify 知识库(RAG),引入真实历史文献作为上下文
- [ ] 增加多轮对话记忆,支持连续追问
- [ ] 拓展 `core_value` 维度,覆盖更多人格类型(如"忧国忧民""玩世不恭""中庸守正")
- [ ] 增加语音输出节点,提升沉浸感
- [ ] 开发简洁前端 UI,脱离 Dify 默认界面

---

## 👤 作者

**王嫣然 (Wang Yanran)**
香港浸会大学(珠海)金融数学专业 · 2024 级
- 📧 Email: yanran060127@gmail.com
- 🏫 BNU-HKBU United International College

---

## 📜 License

本项目采用 [MIT License](LICENSE) 开源协议。
