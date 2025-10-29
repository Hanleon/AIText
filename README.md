🚀 Tencent AI 全流程实践：从注册到部署（前端 + 签名网关 + Nginx/Serverless）

本项目示例以 内容安全 TMS（TextModeration） 为例，演示如何安全地从前端调用腾讯云 AI 能力。你可以按照相同步骤对接其他腾讯 AI 服务（如 ASR、NLP、图像/视频审核等）。

✅ 安全：不在前端暴露 SecretId/SecretKey，通过签名网关/反向代理转发

✅ 支持：Vite/SPA 前端、本地开发代理、宝塔面板（Nginx 反代）、GitHub Pages + Vercel/Cloudflare Workers

✅ 完整：从注册、开通服务、鉴权签名（TC3-HMAC-SHA256）到部署与常见问题排查
