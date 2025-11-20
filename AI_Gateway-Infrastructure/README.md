# 🌉 05.4 AI Gateway Infrastructure

> **Infraestrutura de middleware e gateways para conectar Agentes de IA a dados e serviços de forma segura e escalável.**

Esta seção hospeda a configuração, deploy e documentação das ferramentas que atuam como intermediárias entre nossos modelos de IA (consumidores) e nossos bancos de dados ou APIs externas (provedores).

---

## 🛠️ Ferramentas Implementadas

### 1. Gen AI Toolbox for Databases (Google)
**Função Principal:** Atua como um servidor middleware que expõe ferramentas de banco de dados para agentes de IA (LangChain, etc.) sem expor conexões diretas de SQL.

* **Status:** Ativo
* **Fonte de Dados:** Conecta-se ao nosso PostgreSQL central (alimentado pelo `glowing-system`).
* **Configuração:**
    * Arquivo de definição: [`tools.yaml`](./gen-ai-toolbox/tools.yaml)
    * Variáveis de ambiente: `.env.toolbox`

#### Como Rodar (Docker Compose)

```bash
# Comando para subir o serviço do Toolbox
docker-compose up -d ai-toolbox
```

Tools Disponíveis

Este gateway expõe as seguintes ferramentas para nossos agentes:

- search_social_metrics: Busca dados agregados do glowing-system.

- vector_search_docs: Busca semântica na nossa base de conhecimento.

---
