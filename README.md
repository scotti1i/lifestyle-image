# 生活感生图 · Lifestyle Image

一句话，让 Agent 帮你生成更像日常手机随拍的场景、人像与商品 UGC 图片。

不用自己填写机位、光线、设备表格。Skill 会根据用途补齐拍摄条件，分清参考图的角色，保住人物身份和商品细节，并在出图后检查具体破绽。

## 一条命令安装

先安装 Node.js（包含 `npx`）和 Git，然后在终端运行：

```bash
npx -y skills add scotti1i/lifestyle-image -g --all
```

这会通过 [Skills CLI](https://github.com/vercel-labs/skills) 安装到其支持的 Agent 目录。安装后重新打开 Agent 会话。

只装到 Codex，可用：

```bash
npx -y skills add scotti1i/lifestyle-image -g -a codex -y
```

也可 [下载 ZIP](https://github.com/scotti1i/lifestyle-image/archive/refs/heads/main.zip)，将其中的 `skills/lifestyle-image` 整个目录放入你的 Agent 支持的 skills 目录。

## 直接这样说

在 Codex 中可以显式使用 `$lifestyle-image`：

> 用 $lifestyle-image 生成一个纽约公寓客厅，像普通人用手机拍的。

> 帮我生一张有圣诞装饰的美国家庭客厅，生活一点。

> 用这张人物图和商品图，做一个自然的试穿画面，保留人物身份和衣服结构。

> 这张图有点 AI 感，看看哪里不自然，保留已经好的地方再改。

支持自动发现 Skill 的 Agent 也可以根据请求加载；其他 Agent 按各自的 Skill 调用方式使用。

## 需要什么

这是给 Agent 的生图方法和工作指引，**不包含生图模型、API 密钥或免费额度**。Agent 还需要有可用的图片生成／编辑工具；有内置工具时优先使用内置工具。只有文字能力的环境可以整理提示词，但不能凭安装本 Skill 就生成图片。

使用外部模型时，沿用你配置的渠道、权限与计费方式。无需连接作者的服务，也无需提供作者项目中的素材。

## 沉淀了哪些经验

- 先确定谁在拍、正在做什么、光从哪里来，再写合理可见的细节。
- 人物、商品、空间、原帧参考各有作用，避免把参考中的衣服、妆造和布光一起带入新图。
- 保留自然明暗、肤色和材质；加毛孔、加噪点、做旧、糊脸都不是默认步骤。
- 先看实际输出，再针对手部、接触、镜像、服装串图等问题局部返修；满意就停。
- 跨模型两阶段与真实降级后期按需尝试，保留原版，不承诺它们必然更好。

具体规则见 [手机生活感](skills/lifestyle-image/references/phone-life.md)，实验观察与限制见 [经验依据](skills/lifestyle-image/references/evidence.md)。

## 边界与验证

适用于日常场景、人像、商品 UGC 和已有图片的自然感调整。明确要求的棚拍、插画、电影风格应按原需求执行；不处理文案去 AI 味。

方法来自小样本探索，包含成功与失败经验，没有盲评或通用成功率证明。公开包不附带原始人物照片、商品资产或私有项目。安装检查验证文件完整性，不代表所有 Agent、模型或题材都经过出图测试。

## 文件

```text
skills/lifestyle-image/
├── SKILL.md                 # 入口：理解请求、调用工具、检查与收尾
├── agents/openai.yaml       # Codex 展示与发现配置
└── references/
    ├── phone-life.md        # 核心经验
    └── evidence.md          # 已有观察及适用边界
```

MIT License。
