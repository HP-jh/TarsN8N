# TarsN8N 变更日志

## v1.1.0 (2026-10-18)

### 新增功能
- **n8n_workflow_detail 工具**：通过 ID 获取单个工作流详情，补全 MCP 工具集（原有 list + execute，新增 detail）
- **请求日志中间件**：所有 HTTP 端点自动记录请求方法和耗时，便于运维排查
- **Endpoint 配置校验**：启动时校验 `TARS_MCP_ENDPOINT` 格式，非法 URL 或协议直接报错退出，避免运行时踩坑

### 历史优点整合（自 v1.0.0）
1. **MCP 双模式支持**：stdio（默认）与 HTTP 两种运行模式，兼容 Claude Desktop 与独立部署
2. **安全响应头**：CORS + `X-Content-Type-Options: nosniff` + `X-Frame-Options: DENY`
3. **中文错误信息**：所有用户可见错误均为中文，降低使用门槛
4. **结构化 JSON 响应**：统一返回格式，便于下游解析
5. **环境变量配置**：`TARS_MCP_ENDPOINT` / `TARS_MCP_API_KEY` / `TARS_MCP_MODE` 零代码即可配置
6. **信号处理优雅关闭**：捕获 SIGINT/SIGTERM，资源干净释放
7. **上下文超时控制**：所有上游调用带 5~60 秒超时，防止挂死

### 测试
- 新增 `TestInvokeHandler_WorkflowDetail`：验证 workflow detail 工具接入
- 新增 `TestValidateEndpoint`：验证 endpoint URL 格式校验逻辑
- 全部 7 项测试通过 `go test -race`
