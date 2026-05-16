# 04 配置管理文档

## 1. 配置项范围
### 文档类配置项
- README.md：项目说明、目录结构、分支说明、协作规范
- 01-project-start.md：项目启动说明
- 02-wbs.md：WBS分解文档
- 03-schedule.md：简化进度计划
- 04-config.md：配置管理方案
- docs/conflict.md：冲突模拟与解决文件
- 05-summary-report.md：实验总结报告

### 目录与资源配置项
- src/：示例代码、功能结构文件
- docs/：文档、冲突示例、过程记录
- assets/：图片、说明等资源文件
- test/：测试示例、验证文件

## 2. 分支策略
- main：主分支，保存最终稳定版本，仅允许审核后合并，禁止直接提交
- dev：开发集成分支，所有功能完成后合并到此分支进行验证
- feature-*：功能开发分支，按任务创建，独立修改，完成后合并到dev
- bugfix-*：冲突修复、错误修正分支，用于解决合并问题

## 3. 命名约定
### 文档命名
- 统一格式：数字-英文短横线.md
- 示例：01-project-start.md、02-wbs.md、05-summary-report.md

### 分支命名
- 固定：main、dev
- 功能分支：feature-文档名/任务名
  示例：feature-wbs、feature-schedule、feature-conflict
- 修复分支：bugfix-问题说明
  示例：bugfix-conflict-resolve

### 提交信息规范
格式：类型: 简要描述（英文冒号+空格）
类型包括：
- feat：新增功能/文档
- docs：文档修改
- fix：修复问题/冲突
- merge：合并分支
- refactor：结构调整/优化
  示例：
- docs: 完成WBS三级分解
- fix: 解决conflict.md冲突
- merge: 合并feature-wbs到dev

### Git用户名规范
统一设置为本人姓名全拼，全程不变，便于贡献统计。
示例：zhangsan、liminghao、wangyu

## 4. 合并规则
1. 合并顺序
   feature-* → dev → main

2. 合并责任人
   dev分支：配置管理员（陈文裕）负责合并
   main分支：项目经理（刘广兴）审核后合并

3. 冲突处理规则
    - 禁止自动覆盖冲突
    - 由相关成员共同定位、分析、手工解决
    - 解决后必须提交明确说明
    - 解决完成后再执行合并

4. 合并前检查
    - 拉取最新代码
    - 本地验证文档完整性
    - 确认命名规范、格式正确
    - 确认提交信息规范

## 5. 版本留痕
1. 关键节点版本标记
    - v1.0-init：仓库初始化完成
    - v1.1-start：项目启动说明完成
    - v1.2-wbs：WBS分解完成
    - v1.3-schedule：进度计划完成
    - v1.4-conflict：冲突解决完成
    - v2.0-final：最终版本合并到main

2. 提交历史保留
    - 不使用git push -f强制覆盖
    - 不压缩提交、不删除历史记录
    - 冲突解决前后必须各提交一次
    - 定期提交，不大量修改一次提交

3. 可审计要求
   所有变更可追溯、可对比、可查看作者与时间。