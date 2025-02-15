---
title: "版本更新记录"
group: "关于雷池"
order: 3
---

# 版本更新记录

[版本升级方法](https://waf-ce.chaitin.cn/posts/guide_upgrade)

## [2.2.0] - 2023-07-14

#### 新增

- IP 组中新增长亭社区恶意 IP 情报，内容来自社区版共享的攻击 IP，每日自动更新

#### 优化

- 升级核心检测引擎，修复一些绕过和误报
- 管理界面增加浏览器版本检查，如果版本过旧，会提示升级浏览器
- 优化一些界面的 UI 交互细节
- 修复一些中英文翻译的问题

## [2.1.2] - 2023-07-07

- 修复了日志详情中防护策略模块没有翻译的问题

## [2.1.1] - 2023-07-06

- 修复了防护策略模块没有翻译的问题

## [2.1.0] - 2023-07-06

#### 新增

- 添加/编辑站点时，自动检查端口占用情况，避免保存后配置不生效
- 支持自定义站点的 nginx conf，详情可见[官网文档](https://waf-ce.chaitin.cn/posts/faq_other#%E8%87%AA%E5%AE%9A%E4%B9%89%E7%AB%99%E7%82%B9-nginx-conf)
- [站点列表支持按域名、端口或访问量进行排序](https://github.com/chaitin/safeline/issues/14)
- [绑定 TOTP 密钥时，支持直接复制密钥；登录时的 6 位动态密码输入框，支持粘贴](https://github.com/chaitin/safeline/issues/30)

#### 优化

- [黑白名单和人机验证列表中，可以鼠标悬浮查看 “复合条件” 的具体内容](https://github.com/chaitin/safeline/issues/120)
- 修复人机验证列表中，“源 IP 不属于 IP 组” 的规则，IP 组名称显示成了 id 的问题
- [优化人机验证启用/禁用交互](https://github.com/chaitin/safeline/issues/130)
- [优化描述文字](https://github.com/chaitin/safeline/issues/122)
- 优化一些界面 UI 交互、提示文字
- 修复一些已知问题

## [2.0.1] - 2023-06-30

- 调整了人机验证的策略，降低误拦的情况
- 修复了人机验证启动/禁用规则不会自动刷新状态的问题
- 修复其他一些已知问题

## [2.0.0] - 2023-06-29

#### 新增

- 人机验证
- 支持嵌入式部署，可以通过 [t1k 协议](https://github.com/chaitin/lua-resty-t1k) 直接把流量转发到雷池进行检测
- 把日志详情中的源 IP 加入到 IP 组时，支持调整 IP 为任意 IP 或网段

#### 优化
- 日志列表按照时间和 ID 排序，防止出现小范围的时间乱序
- 转发流量时，自动设置请求头 X-Forwarded-Proto，适配更多代理场景
- 优化界面 UI，修复其他一些已知问题

## [1.10.0] - 2023-06-21

#### 新增

- 防护站点新增 “运行模式”，可以一键将站点设为 观察 或 维护 模式了

#### 优化

- 修复了站点列表没有分页器的问题
- 修复了窗口水平滚动时导航栏会错位的问题
- 修复了黑白名单配置 “不属于 IP 组” 的条件时，列表显示组 ID，而未显示组名称的问题
- 优化了界面的 UI 与交互

## [1.9.0] - 2023-06-16

#### 新增

- 界面 UI 改造，信息层级更清晰
- 黑白名单支持添加 源 IP - 不属于 IP 组 的条件

#### 优化

- 检测日志的路由进一步完善
- 数据统计页面更加紧凑，现在可以在 1920*1080 的屏幕上完全显示了
- 黑白名单的展示优化
- 修复 通用配置-防护模块配置 中，“批量配置为” 按钮有时候不生效的问题
- 修复一些已知问题

## [1.8.2] - 2023-06-12

- 修复了「30 天访问情况」和「30 天拦截情况」显示相同数据的问题

## [1.8.1] - 2023-06-09

- 修复了「全部请求」和「仅拦截」数据一样的问题

## [1.8.0] - 2023-06-09

#### 新增

- 数据统计页面增加访问来源地区、流量统计，更好把控网站运营情况

![](/images/docs/about_changelog/map.png)

#### 优化

- 更新语义引擎版本，优化了一大批检测逻辑，降低误报
- 优化了部分操作提示信息：
  - IP 组正在使用时，无法被删除的提示
  - 未创建 IP 组时，在黑白名单中无法选择属于 IP 组的提示
  - 添加站点时，域名格式错误的提示

## [1.7.1] - 2023-06-05

#### 修复
- 部分情况下无法打开日志详情页面的问题
- 部分情况下页面查询数量只有 10 条的问题

## [1.7.0] - 2023-06-01

#### 新增
- 新增 “IP 组” 功能，可以快速配置大量 IP 的黑/白名单了
- 防护策略增加 “仅观察” 配置
- 防护策略增加 “批量配置为” 按钮，可以快速切换所有模块的防护策略

#### 优化
- 自定义规则列表增加翻页
- 优化规则生效顺序，现在会优先执行完所有白名单，再执行黑名单

## [1.6.0] - 2023-05-25

#### 新增
- 自定义规则支持匹配 Header 和 Body
- 检测日志支持按域名搜索
- 支持命令行清理检测日志和统计信息

## [1.5.1] - 2023-05-18

- 修复了自定义规则切换白名单之后，无法创建/编辑的问题

## [1.5.0] - 2023-05-18

#### 新增
- 支持 i18n
- 数据统计新增 “今日请求错误情况”
- 检测日志的筛选条件现在会显示在 URL，方便保存

#### 优化
- 修复自定义规则的编辑表单，有时候会丢失编辑中数据的问题
- 修复 Safari 浏览器上的一些显示问题
- 修复 Payload 中存在非 Unicode 编码时，检测日志会入库失败的问题（不影响拦截）
- 修复新增的 “HTTP 请求走私” 攻击类型会被错误地展示成 “未知” 攻击类型的问题

## [1.4.0] - 2023-05-12

#### 新增
- 自定义规则支持匹配域名
- 支持在一条自定义规则内，设置多个匹配条件
- 站点列表新增 “今日访问 / 拦截量”

#### 优化
- 优化交互和提示文案、修复已知问题

## [1.3.0] - 2023-05-05

#### 新增
- 支持按照源 IP、攻击类型、URL 筛选检测日志

#### 修复
- 修复 dashboard 在部分低版本浏览器下的兼容问题
- 修复按源 IP 添加自定义规则时，添加不了 /8 和更大的网段的问题

## [1.2.0] - 2023-04-27

#### 新增
- 新增了数据统计页面，可以直观的看到流量大小
- 支持配置源 IP 提取方式，解决了源 IP 获取不对的问题
- 支持自定义检测策略，可以动态调整检测引擎

## [1.1.0] - 2023-04-20

#### 新增
- 支持根据 IP 和 URL 特征配置黑白名单
- 默认开启高防模式

#### 优化
- 支持在日志详情中展示响应报文
- 服务器时间不准导致 TOTP 无法登录时增加了提示语
- 修复了上游服务器填 HTTPS 时端口解析不正确的问题
- 优化了 SSL 上传逻辑，体验更好

## [1.0.0] - 2023-04-13

- 站点配置

## [0.9.0] - 2023-03-20

- OTP 登录
- 攻击检测日志
- 默认防护策略
