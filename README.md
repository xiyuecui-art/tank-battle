# 坦克大战 Tank Battle

一个用纯 HTML5 / CSS / JavaScript（无任何依赖）实现的红白机经典游戏 **《坦克大战》（Battle City）** 复刻版。单文件 `index.html`，双击即可在浏览器中游玩。

## ✨ 特性

- 🎮 方向键 / WASD 控制移动，空格射击
- 🧱 可摧毁的砖墙（土墙）与不可摧毁的钢墙
- 🦅 需要守护的总部（基地），被敌方击中即失败
- 🤖 敌方坦克 AI：随机巡游、智能追击、主动开火、会拆墙开路
- ❤️ 生命值 + 重生无敌时间
- 📈 计分与关卡递进（敌军数量随关卡增加）
- 💥 爆炸粒子特效、音效（WebAudio，浏览器本地生成）
- ⏸️ 暂停（P）、静音（M）

## 🚀 运行方式

直接双击 `index.html` 用浏览器打开即可，无需安装任何依赖。

或启动一个本地静态服务器：

```bash
python -m http.server 8000
# 然后访问 http://localhost:8000
```

也可以在线试玩（GitHub Pages）：<https://YOUR_USERNAME.github.io/tank-battle/>

## 🕹️ 操作说明

| 按键 | 功能 |
| --- | --- |
| `↑` `↓` `←` `→` / `WASD` | 移动 & 转向 |
| `空格` / `J` | 射击 |
| `P` | 暂停 / 继续 |
| `M` | 静音开关 |
| `Enter` | 开始 / 重新开始 |

## 📐 实现思路

- 基于 HTML5 Canvas 渲染，`requestAnimationFrame` 游戏循环
- 网格地图（20×14，每格 32px），砖墙 / 钢墙 / 基地三种地形
- 实体（坦克、子弹）采用轴对齐包围盒（AABB）碰撞检测，移动时按网格吸附保证对齐
- 敌方 AI：定时随机转向 + 概率性朝向玩家追击，撞墙即时改向
- 模块化状态机：`menu / playing / paused / gameover / win`

## 📄 许可证

[MIT](./LICENSE)