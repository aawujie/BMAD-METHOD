# BMAD-METHOD Web Bundles 使用笔记

## 什么是Web Bundles
- Web Bundles是BMAD-METHOD框架为网页AI平台(如ChatGPT、Claude、Gemini)设计的单文件包
- 它们将代理(agents)、任务、模板等内容打包成单一文本文件
- 使得BMAD方法可以在不支持文件系统的网页AI界面中使用

## Web Bundles类型
1. **单个代理bundles**
   - 位于`dist/agents/`目录
   - 如`analyst.txt`、`dev.txt`等独立代理文件

2. **团队bundles**
   - 位于`dist/teams/`目录
   - 包含多个代理及其依赖资源
   - 适用于需要协作的复杂场景

3. **扩展包bundles**
   - 位于`dist/expansion-packs/`目录
   - 包含特定领域的专业功能(如游戏开发、DevOps等)

## 如何使用Web Bundles
1. **安装与选择**
   - 在BMAD安装过程中选择"Include web bundles"
   - 可选择全部bundles、特定团队、单个代理或自定义选择
   - 默认安装到`<安装目录>/web-bundles`

2. **上传到AI平台**
   - 复制选择的bundle文件(`.txt`)内容
   - 将内容粘贴到网页AI平台(如ChatGPT、Claude等)的对话中
   - AI将自动识别并激活相应的BMAD代理

3. **交互使用**
   - 根据AI的指引与代理进行交互
   - AI能够通过bundle中的标记找到所需资源
   - 所有必要的知识和工具都已包含在单一bundle文件中

## 适用场景
- 在网页AI平台上进行项目规划、需求分析
- 不想或无法使用IDE插件时的替代方案
- 分享BMAD工作流给没有完整安装的同事

## 注意事项
- Web bundles可能较大(特别是团队bundles)
- 使用前应确认AI平台的上下文窗口大小是否足够
- 部分AI平台可能对输入长度有限制，考虑使用单个代理而非完整团队
- 使用前先执行`npm run build`确保bundles是最新的

## 构建自定义Bundles
如需构建自定义bundles:
```
# 构建所有bundles
npm run build

# 仅构建特定代理
npm run build:agent <agent-id>

# 仅构建特定团队
npm run build:team <team-id>

# 构建扩展包
npm run build:expansions
```

---
BMAD-METHOD web bundles为在网页AI平台上使用高级代理工作流提供了简便解决方案，无需复杂安装，只需上传单一文本文件即可使用完整功能。 