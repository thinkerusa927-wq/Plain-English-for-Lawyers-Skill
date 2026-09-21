# Plain English Drafting

一个用于英文起草、修改和提意见的 Codex 技能，适用于邮件、协议、条款及其他商务或法律文本。

技能入口使用中文。全部英文表述规则以 [`references/plain-english-rules.md`](references/plain-english-rules.md) 为准。该文件完整保留用户提供的 `Plain English Skill.md`，仅调整文件名，未修改内容。`SKILL.md` 负责说明适用范围和调用方式，不另写英文表述规则。

## 适用场景

- 起草英文邮件、协议或条款。
- 修改、润色已有英文文本。
- 对英文表述提出修改意见。
- 将中文或其他语言的商务、法律文本翻译成英文。

每次调用时，技能要求先完整阅读规则原文，再根据本次请求交付文本、修改稿或修改意见。

## 文件结构

```text
draft-plain-english/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── plain-english-rules.md
```

| 文件 | 用途 |
| --- | --- |
| [`SKILL.md`](SKILL.md) | 中文技能入口与适用范围 |
| [`references/plain-english-rules.md`](references/plain-english-rules.md) | 英文表述规则的唯一来源 |
| [`agents/openai.yaml`](agents/openai.yaml) | Codex 中的显示信息、示例提示词及自动匹配配置 |

## 安装到 Codex

下载本仓库，将包含 `SKILL.md` 的整个目录命名为 `draft-plain-english`，放入 Codex 的技能目录：

- 已设置 `CODEX_HOME`：放入其下的 `skills` 目录。
- 未设置 `CODEX_HOME`：放入用户主目录下的 `.codex/skills` 目录。

安装后的结构应为：

```text
<Codex 配置目录>/skills/draft-plain-english/SKILL.md
<Codex 配置目录>/skills/draft-plain-english/agents/openai.yaml
<Codex 配置目录>/skills/draft-plain-english/references/plain-english-rules.md
```

保留目录结构，以便技能通过相对路径读取规则文件。若已有同名技能，请先保留需要的旧版本，再进行替换。

## 使用方法

可以显式指定技能：

```text
使用 $draft-plain-english，帮我起草一封英文邮件，内容如下：……
```

```text
使用 $draft-plain-english，修改以下英文条款：……
```

```text
使用 $draft-plain-english，对以下英文协议提出修改意见：……
```

技能已启用自动匹配，也可直接提出相应英文写作请求；显式指定技能名称可以明确本次使用意图。

涉及合同实质审阅、文档制作、模板处理或邮件个人风格时，可配合相应技能使用。英文表述规则仍以引用的原文为准；用户当前明确要求优先。

## 上传到 GitHub

将本目录中的文件和子目录直接放在仓库根目录，使仓库首页展示本 README。仓库可命名为 `draft-plain-english`。

所有文件引用均为相对路径，不依赖创建者的本地目录。使用该技能无需额外脚本或 API 密钥。

## 维护约定

规则原文应完整保留，包括措辞、数字、示例、标点和原有拼写。未经用户明确要求，不修改、纠错、删减或增补该文件。

维护技能入口或 README 时，通过链接引用原文，不另行复制、概括或解释其中的英文表述规则。
