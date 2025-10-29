🚀 一个可以读取word文件，检测是否AI文字的在线工具。
---
测试地址：

https://hanleon.cc/AIText/
---
## 🧭 使用说明（Usage Guide）

本项目基于 **腾讯云·文本内容安全（Text Moderation）API**，提供文本与文档的智能内容检测功能。  
请在使用前，按照以下步骤完成配置与操作。

---

### ⚙️ 一、前置条件

1. **注册并登录腾讯云账号**  
   前往 [腾讯云官网](https://cloud.tencent.com/)，完成实名认证。  

2. **开通内容安全（TMS）服务**  
   在控制台搜索 “内容安全（Text Moderation）” 并开通此服务。  
   记录接口域名：`tms.tencentcloudapi.com`  

3. **创建访问密钥（SecretId / SecretKey）**
   
   前往 [api页面](https://console.cloud.tencent.com/cam/capi)SecretId和SecretKey
   前往 [cms页面](https://console.cloud.tencent.com/cms)获取BizType
   - 打开「访问管理（CAM）」 → 「访问密钥」 → 新建密钥  
   - 复制并妥善保管 SecretId 与 SecretKey（后续将在网页端填写）  
   - 创建业务策略 获取 BizType
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/cb5c83e3-03b9-4867-9c75-417e9f25835c" />
  
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/b8d610e4-e27e-4590-b7b7-751aedff1962" />

---

### 🚀 二、使用步骤

1. **部署项目**  
   将项目部署至本地或服务器环境后，访问前端页面。

2. **填写密钥信息**  
   页面顶部输入框中依次输入：
   - `SecretId`
   - `SecretKey`
   - `BizType`（业务策略，可在腾讯云控制台自定义或留空使用默认策略）

3. **点击检测**  
   填写完成后，点击 **“发送检测”** 按钮，即可发起文本审核请求。

4. **查看检测结果**  
   页面将显示返回的 AI 检测结果：
   - **AI 分数（Score）**：代表模型判断内容“AI生成”或“违规倾向”的置信度；
   - **分数越低越安全**，说明内容风险越低或更偏向人工生成。

---

### ✏️ 三、页面功能说明

整个页面分为 **两大功能区块**：

#### ① 文本内容检测区  
- 直接在输入框中粘贴或输入任意文本  
- 点击「发送检测」即可立即获得腾讯 AI 审核结果  
- 适合短文、评论、段落内容的快速检测  

#### ② 文档批量检测区  
- 支持上传 `.docx` 或 `.txt` 文件  
- 系统将自动 **切片处理** 文档（按段落拆分）  
- 点击「一键识别」后，将自动逐段调用 AI 接口  
- 最终展示每段的 **AI 占比分析结果**，帮助判断整体 AI 生成程度  

---

### 📊 四、结果说明

| 指标 | 含义 | 建议 |
|------|------|------|
| **Score** | AI 模型输出分值 | 越低越好 |
| **Suggestion** | 是否通过 | Pass/Block/Review |
| **Label** | 标签 | 正常为Normal/AI文字为GeneratedContentRisk  |
| **SubLabel** | 文本类型 | AI生成为AITextGenerated  |

---

### 💡 提示

- 支持自定义 **BizType 策略**，以适应不同内容审核标准。  
- 若腾讯云接口调用次数超出免费额度，可在控制台购买更高配额。  
- 若返回 `403` 或签名错误，请检查 `SecretKey` 是否正确、时间戳同步是否正常。  

---

📘 **示例截图：**

<img width="500" alt="image" src="https://github.com/user-attachments/assets/07f11c8e-7b9e-4c4f-987d-3a456d0d76e8" />

---
