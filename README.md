Web电商平台项目文档 
 
项目概述 
 
这是一个基于SpringBoot + Vue前后端分离架构实现的现代化电商平台，采用了当前主流的技术栈和架构设计，实现了商品展示、购物车、订单管理、支付集成等核心电商功能。
 
技术栈 
 
后端技术栈 
 
- 核心框架: Spring Boot 2.7.x 
- 安全框架: Spring Security + JWT 
- 持久层: MyBatis-Plus 3.5.x 
- 数据库: MySQL 8.0 + Redis 7.0 
- 搜索引擎: Elasticsearch 8.x 
- 消息队列: RabbitMQ 3.11 
- 文件存储: MinIO (自托管对象存储)
- API文档: Swagger + Knife4j 
- 构建工具: Maven 3.8+
- 部署: Docker + Docker Compose 
 
前端技术栈 
 
- 核心框架: Vue 3.x + Composition API 
- UI组件库: Element Plus 2.3.x 
- 状态管理: Pinia 2.0.x 
- 路由管理: Vue Router 4.x 
- HTTP客户端: Axios 1.3.x 
- 构建工具: Vite 4.x 
- 可视化图表: ECharts 5.4.x 
- 代码规范: ESLint + Prettier 
 
系统架构 
 
整体架构 
 
本项目采用前后端分离架构，主要分为以下几层：
 
1. 前端展示层: Vue构建的SPA应用，负责用户界面展示和交互 
2. API网关层: Spring Cloud Gateway统一路由和鉴权 
3. 业务服务层: 多个微服务处理核心业务逻辑 
4. 数据存储层: 关系型数据库+缓存+搜索引擎 
5. 基础设施层: 文件存储、消息队列等中间件 
 
微服务划分 
 
1. 用户服务: 处理用户注册、登录、权限管理 
2. 商品服务: 商品CRUD、分类管理、搜索服务 
3. 订单服务: 订单创建、状态管理、物流跟踪 
4. 支付服务: 支付渠道集成、交易记录 
5. 促销服务: 优惠券、秒杀活动、积分系统 
 
功能模块 
 
核心功能 
 
1. 用户系统
   - 注册/登录(手机号+验证码、账号密码)
   - JWT身份认证 
   - 角色权限管理 
   - 个人信息维护 
 
2. 商品系统
   - 多级商品分类 
   - 商品SPU/SKU管理 
   - 商品评价 
   - 商品搜索(支持Elasticsearch全文检索) 
   - 商品收藏 
 
3. 购物流程
   - 购物车管理 
   - 订单创建与支付 
   - 订单状态跟踪 
   - 退货退款处理 
 
4. 营销系统
   - 优惠券发放与使用 
   - 秒杀活动 
   - 积分商城 
   - 会员等级 
 
扩展功能 
 
1. 数据统计与分析看板 
2. 物流跟踪API集成 
3. 多支付渠道对接(微信、支付宝)
4. 第三方登录(微信、QQ)
5. 消息通知(站内信、短信、邮件)
 
项目结构 
 
```
├── e-commerce-platform 
│   ├── eureka-server/           # 服务注册中心 
│   ├── api-gateway/              # API网关 
│   ├── user-service/             # 用户服务 
│   ├── product-service/          # 商品服务 
│   ├── order-service/            # 订单服务 
│   ├── payment-service/          # 支付服务 
│   ├── promotion-service/        # 促销服务 
│   └── config/                   # 公共配置 
├── frontend/                     # 前端项目 
│   ├── public/                   # 静态资源 
│   ├── src/
│   │   ├── api/                  # API请求封装 
│   │   ├── assets/               # 静态资源 
│   │   ├── components/           # 公共组件 
│   │   ├── router/               # 路由配置 
│   │   ├── stores/               # 状态管理 
│   │   ├── utils/                # 工具函数 
│   │   ├── views/                # 页面组件 
│   │   ├── App.vue               # 根组件 
│   │   └── main.js               # 入口文件 
│   └── vite.config.js            # Vite配置 
├── docker-compose.yml            # Docker编排文件 
├── README.md                     # 项目文档 
└── .gitignore                    # Git忽略配置 
```
 
开发环境搭建 
 
后端环境 
 
1. 安装JDK 17+
2. 安装Maven 3.8+
3. 安装MySQL 8.0+
4. 安装Redis 7.0+
5. 安装Elasticsearch 8.x 
6. 安装RabbitMQ 3.11 
 
前端环境 
 
1. 安装Node.js 16+
2. 安装pnpm或npm/yarn 
3. 安装VSCode或WebStorm等IDE 
 
部署说明 
 
本项目支持多种部署方式：
 
1. 传统部署: 分别打包前后端项目，部署到服务器 
2. Docker部署: 使用提供的docker-compose.yml一键部署 
3. Kubernetes部署: 提供k8s部署模板(可选)
 
特色与优势 
 
1. 前后端分离: 清晰的责任划分，提高开发效率 
2. 微服务架构: 高内聚低耦合，易于扩展和维护 
3. 性能优化: 多级缓存、异步处理、CDN加速 
4. 安全防护: JWT认证、接口防刷、SQL注入防护 
5. 可观测性: 集成Prometheus+Grafana监控 
 
许可证 
 
本项目采用MIT开源协议，可自由用于学习和商业用途。
