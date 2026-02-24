# yihen-drama（后端服务）

## 技术栈
- Java 17
- Spring Boot 3
- MyBatis-Plus
- MySQL 8 / Redis / RabbitMQ
- Elasticsearch 8 + IK/pinyin
- MinIO

## 本地运行

```bash
cd yihen-drama
mvn spring-boot:run
```

默认端口：`8080`

## 依赖服务

建议使用根目录编排启动中间件：

```bash
docker compose -f ../docker-compose.infra.yml up -d --build
```

## 关键配置

配置文件：`src/main/resources/application.yml`  
支持环境变量覆盖，核心项：
- `SPRING_DATASOURCE_*`
- `SPRING_DATA_REDIS_*`
- `SPRING_RABBITMQ_*`
- `SPRING_ELASTICSEARCH_URIS`
- `MINIO_*`

## API 文档

启动后访问：
- `http://localhost:8080/doc.html`

## 初始化 SQL

- 文件：`sql/init_schema.sql`
- Docker MySQL 首次启动时自动执行

