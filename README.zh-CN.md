# codex-pet-collection

为 [Codex CLI](https://codex-pet.org) 与 [CC-Haha](https://github.com/) 制作的动画桌宠合集，收录 **《碧蓝档案》的伊落玛丽** 两个版本：**偶像玛丽** 与 **体操玛丽**，均为 9 状态精灵动画。

> [!TIP]
> **快速跳转：** [桌宠一览](#-桌宠一览) · [安装](#-安装) · [文件格式](#-文件格式与自制方法) · [致谢](#-致谢) · [English](README.md)

---

## 🐾 桌宠一览

### 偶像玛丽 `mari-idol`

> "其实……我一直憧憬着，成为偶像。—— 愿这首歌能够传递给您"

隶属圣三一综合学园修女会，偶像团体 **Antique Seraphim** 的领队。她站上舞台，只是想让大家都变得幸福。

| 待机预览 | 规格 |
|---|---|
| ![偶像玛丽待机动画](pets/mari-idol/preview.gif) | 9 状态 · 6×9 网格 · 每帧 256×208 px |

- **Petdex 页面：** [#4306 → mari-2](https://petdex.dev/pets/mari-2)
- **codex-pet.org 页面：** [mari](https://codex-pet.org/pets/mari/)

### 体操玛丽 `mari-gym`

> "希望大家能带着微笑度过这次的大运动会"

为晄轮大祭换上体育服的修女会少女——自愿接下实行委员工作，却因天生献身性格一直被卷入各种麻烦。

| 待机预览 | 规格 |
|---|---|
| ![体操玛丽待机动画](pets/mari-gym/preview.gif) | 9 状态 · 6×9 网格 · 每帧 256×208 px |

- **Petdex 页面：** [mari-gym](https://petdex.dev/pets/mari-gym)

---

## 📦 安装

### 通过 Petdex（推荐）

```bash
npx petdex install mari-2      # 偶像玛丽
npx petdex install mari-gym    # 体操玛丽
```

适用于 **Codex**、**ChatGPT 桌面版**、**Petdex Desktop**。

### 通过 codex-pet.org

```bash
npx codex-pet-installer add mari
```

### 手动安装

克隆本仓库（或直接下载 ZIP），把想要的宠物文件夹拷过去：

```bash
git clone <repository-url>

# CC-Haha — 拷到 ~/.claude/cc-haha/pets/
cp -r codex-pet-collection/pets/mari-idol ~/.claude/cc-haha/pets/
cp -r codex-pet-collection/pets/mari-gym ~/.claude/cc-haha/pets/

# Codex CLI / 其他遵循 codex-pet 布局的客户端
cp -r codex-pet-collection/pets/mari-idol ~/.codex/pets/   # 按你客户端的 pets 目录调整
```

每个宠物文件夹都是独立可用的：`pet.json`（元数据）+ `spritesheet.png`（全部帧）。拷贝后重启客户端即可。

---

## 🗂 文件格式与自制方法

```
pets/
├── mari-idol/
│   ├── pet.json          # id / 显示名 / 描述 / 精灵版本号
│   ├── spritesheet.png   # 1536×2288 RGBA，6 列 × 9 行，每帧 256×208 px
│   └── preview.gif       # 待机动画循环预览（README 用）
└── mari-gym/
    └── …
```

**动画状态**（精灵图每一行对应一个状态，自上而下）：

| 行 | 状态 | 行 | 状态 |
|---|---|---|---|
| 1 | 待机 Idle | 6 | 失败 Failed |
| 2 | 向右跑 Run right | 7 | 等待 Waiting |
| 3 | 向左跑 Run left | 8 | 奔跑 Running |
| 4 | 挥手 Waving | 9 | 审阅 Review |
| 5 | 跳跃 Jumping | | |

`pet.json` 字段说明：

```jsonc
{
  "id": "mari",                    // 加载器使用的唯一 id
  "displayName": "偶像玛丽",        // 切换器里显示的名字
  "description": "…",              // 角色介绍文案
  "spriteVersionNumber": 2,        // 精灵图格式版本
  "spritesheetPath": "spritesheet.png"
}
```

**自制一只桌宠只需三步：**

1. 画一张精灵图：**6 列 × 9 行**，每格 **256×208 px**，透明背景——第 *n* 行对应上表第 *n* 个状态，帧从左到右播放。
2. 填一份 `pet.json`（字段见上）。
3. 把文件夹放进客户端的 pets 目录，重启即可。

---

## 🏷 搜索标签

`碧蓝档案` · `blue-archive` · `mari` · `伊落玛丽` · `圣三一` · `桌宠` · `desktop pet` · `codex pet` · `spritesheet` · `像素画` · `同人`

## 🙏 致谢

- **精灵图绘制** — [Project Contributors](<account-url>)
- **角色出处** — 《碧蓝档案》(Blue Archive) 伊落マリー / Iochi Mari © Nexon Games / Yostar。本仓库为非官方同人作品，角色版权归原权利方所有。
- **发布平台** — [Petdex](https://petdex.dev) · [codex-pet.org](https://codex-pet.org) 社区

## 📄 许可证

本仓库的代码与打包结构采用 [MIT License](LICENSE)。
精灵图属于受版权保护角色的同人作品：仅限非商业用途，角色一切权利归《碧蓝档案》权利方所有。
