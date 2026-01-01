# 🖼️ 图片背景移除工具

一个基于HTML5 Canvas的在线图片背景移除工具，使用洪水填充算法精确去除图片背景。

## ✨ 主要特性

- 🎯 **智能颜色采样**: 采用十字形21像素采样技术，提高颜色识别精度
- 🖱️ **直观操作**: 点击图片即可选择背景颜色，实时预览效果
- 📁 **多种上传方式**: 支持拖拽上传和点击选择文件
- 🎨 **透明背景预览**: 使用棋盘格背景清晰显示透明区域
- ⚡ **高性能处理**: 优化的事件处理和内存管理
- 🔧 **精确控制**: 可调节颜色相似度阈值
- 💾 **一键下载**: 处理完成后直接下载PNG格式图片

## 🚀 快速开始

### 在线使用
直接打开 `移除背景.html` 文件即可使用，无需安装任何依赖。

### 本地部署
```bash
# 克隆项目
git clone https://github.com/657258535/Image-Background-Removal
cd remove-background

# 启动本地服务器（可选）
python -m http.server 8000
# 或者
npx serve .
```

然后在浏览器中访问 `http://localhost:8000`

## 📖 使用说明

### 1. 上传图片
- **拖拽上传**: 将图片文件拖拽到预览区域
- **点击上传**: 点击上传按钮选择图片文件

支持格式：JPG, PNG, WebP, GIF等常见图片格式

### 2. 选择背景颜色
- 点击图片上的任意位置
- 系统会从点击位置向四个方向各采集5个像素（总共21个像素）
- 计算这21个像素的平均颜色作为目标背景色

### 3. 调节参数
- **相似度阈值**: 调节颜色匹配的敏感度
  - 数值越小：只替换非常相似的颜色
  - 数值越大：替换相似度较低的颜色

### 4. 下载结果
- 处理完成后点击"下载图片"按钮
- 系统会生成PNG格式的透明背景图片

## 🎯 技术特点

### 核心算法
- **十字形采样**: 21像素采样提高颜色识别准确性
- **洪水填充算法**: 高效的区域填充和边界检测
- **像素级处理**: 精确到单个像素的颜色操作

### 性能优化
- **事件节流**: 使用 `requestAnimationFrame` 优化鼠标移动事件
- **内存管理**: 自动清理画布资源和事件监听器
- **异步处理**: 使用 async/await 提升代码可读性和性能

### 用户体验
- **实时反馈**: 显示处理进度和状态信息
- **友好提示**: 智能检测无效操作并给出提示
- **视觉辅助**: 透明背景预览和步骤指示器

## 🛠️ 技术栈

- **前端**: HTML5, CSS3, JavaScript (ES6+)
- **Canvas API**: 图片像素级操作和处理
- **算法**: 洪水填充算法, 颜色距离计算
- **UI**: 响应式设计, 拖拽交互

## 📁 项目结构

```
移除背景/
├── index.html          # 主要的HTML文件
├── TransparentBackground.png  # 透明背景图案
└── README.md              # 项目说明文档
```

## 🔧 开发说明

### 核心类和方法

```javascript
class ImageProcessor {
    // 核心功能类
    async processImage(file)        // 图片加载和初始化
    collectCrossPixels()            // 十字形21像素采样
    floodFillTransparent()          // 洪水填充算法
    calculateAverageColor()         // 平均颜色计算
    rgbToHex()                      // 颜色格式转换
}
```

### 关键算法

#### 1. 十字形采样算法
```javascript
// 从中心点向四个方向各采集5个像素
// 总共21个像素用于颜色分析
collectCrossPixels(centerX, centerY, ctx, width, height)
```

#### 2. 洪水填充算法
```javascript
// 检测并替换连续的颜色区域
floodFillTransparent(imageData, width, height, startX, startY, targetColor, tolerance)
```

## 📱 浏览器兼容性

- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ 移动端浏览器

## 🚧 功能改进

- [ ] 支持多种输出格式 (WebP, JPG)
- [ ] 添加图片缩放和裁剪功能
- [ ] 实现批量处理模式
- [ ] 添加更多的处理算法
- [ ] 支持历史操作撤销
- [ ] 添加键盘快捷键支持

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

### 开发环境设置
1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

### 代码规范
- 使用 ES6+ 语法
- 保持代码清晰和注释完整
- 遵循现有的代码风格

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 👨‍💻 作者

**开发者**: AI Assistant  
**项目类型**: 图片处理工具  
**开发时间**: 2026年  

## 🙏 致谢

- 感谢 HTML5 Canvas API 提供的强大图片处理能力
- 感谢现代浏览器的出色性能和兼容性支持
- 感谢开源社区的无私分享和学习资源

## 📞 联系方式

如有问题或建议，请通过以下方式联系： Issues

---

⭐ 如果这个项目对您有帮助，请给它一个星标！
