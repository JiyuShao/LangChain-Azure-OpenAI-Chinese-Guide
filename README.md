# LangChain + Azure OpenAI 中文教程

## 介绍

**首先感谢[《LangChain 中文入门教程》](https://github.com/liaokongVFX/LangChain-Chinese-Getting-Started-Guide)提供的教程，本教程是在该教程的基础上修改而来。主要改动如下：**

- 改动一：使用 Azure OpenAI 替换 OpenAI
  _由于 OpenAI 在国内申请困难，而 Azure OpenAI 的申请较为简单，所以选择使用 Azure OpenAI 来。_

- 改动二：更新已经过时的 LangChain 调用方式
  _由于该文档的编写时间是 2023 年 4 月初，有些代码和模型已经过时，所以本文更新了模型与其调用的方式_

## 账号申请

### 0. 申请 OpenAI 遇到的坑

在申请 OpenAI 账号的时候遇到很多坑：

- 要清空缓存翻墙，而且还要多换几次，因为翻墙的 IP 有可能已被拉入黑名单（这个可以忍）
- 需要绑定国外的手机号（忍了）
- 需要有国外的信用卡，虚拟信用卡还被封（怎么搞都搞不好，去他妹的）

而且我之前就申请过 OpenAI 账号，所以免费的使用额度已经过期了，所以还是使用 Azure OpenAI 吧。

### 1. 申请 Azure OpenAI 账号

微软的 Azure OpenAI Service 服务允许绑定国内的信用卡，具体的教程可以看[这个](https://www.youtube.com/watch?v=-RI2pXNfOKQ&ab_channel=AI%E5%AD%A6%E9%95%BF%E5%B0%8F%E6%9E%97)。

### 2. 创建 Deployment

在申请完 Azure OpenAI 之后，需要创建部署，[可选模型](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models)如下：

- gpt-35-turbo
- gpt-35-turbo-16k
- text-embedding-ada-002
- 其中 GPT-4 需要额外申请资格，见[申请链接](https://aka.ms/oai/get-gpt4)。

### 3. 关闭敏感词过滤

Azure OpenAI 的模型返回时不时会被 [Content filtering](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/content-filter) 挡掉，想关掉的话需要去额外申请 Modified Content Filters and Abuse monitoring

### 4. 体现本项目

- 创建 `src/config/.env` 环境变量

- 打开 `src\index.ipynb` 开始愉快的玩耍吧
