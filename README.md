# 🤖 Assistente de Investimentos com RPA e IA Generativa

Projeto prático desenvolvido no **Bootcamp Santander 2026** através da [DIO](https://dio.me).

---

## 🎯 Sobre o Projeto
Pipeline automatizado de RPA (Robotic Process Automation) que extrai dados de clientes de uma página web, cruza seus perfis com opções reais de investimentos e utiliza Inteligência Artificial para gerar e disparar recomendações financeiras personalizadas via e-mail.

---

## 🏗️ Arquitetura da Solução
1. **Extração (Python + BeautifulSoup):** Robô que raspa uma tabela HTML de clientes na web e envia via requisição HTTP POST para o orquestrador.
2. **Orquestração (n8n):**
   - **Webhook:** Recebe o lote de clientes.
   - **HTTP Request:** Faz o download automático da base de investimentos (`data.csv`).
   - **Code (JavaScript):** Faz o cruzamento de regras de negócio (perfil do investidor x saldo mínimo).
   - **OpenAI (LLM):** Redige e-mails personalizados em formato JSON (assunto, texto e HTML) sem promessas irreais de ganho.
   - **IF (Validação):** Valida o formato dos e-mails via Regex para segurança antes do disparo.
   - **Gmail:** Envio automático das mensagens para os clientes.

---

## 🛠️ Tecnologias Utilizadas
- **Python** (Web Scraping com `requests` e `BeautifulSoup`)
- **n8n** (Orquestração de workflows low-code)
- **OpenAI API** (IA Generativa para copywriting personalizado)
- **Gmail API** (Disparo automatizado de e-mails)
- **GitHub & GitHub Pages** (Hospedagem e versionamento)

---

## 🚀 Como Executar
1. Importe o arquivo `workflow.json` no seu ambiente do n8n.
2. Configure suas credenciais da OpenAI e do Gmail no n8n.
3. Execute o script `extrair_clientes.ipynb` no Google Colab ou máquina local para disparar os dados para o Webhook do n8n.
