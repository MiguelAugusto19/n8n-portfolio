# 🚀 Disparador em Massa (WhatsApp Automático via N8N)

Este workflow automatiza o envio de mensagens personalizadas via WhatsApp para listas de leads frios, utilizando IA (OpenAI) para variar o texto, e tempo aleatório entre os envios para evitar bloqueios.

---

## 💼 Aplicação

Ideal para:
- SDRs, pré-vendedores ou consultores comerciais
- Campanhas outbound com contatos frios
- Prospecção automatizada via WhatsApp com segurança

---

## ⚙️ O que esse workflow faz

1. Recebe dados via Webhook (nomes, números, mensagem, cidade, etc.)
2. Separa os campos recebidos em arrays
3. Roteia os dados conforme o tipo de envio (ex: texto ou imagem)
4. Itera sobre os leads com `SplitOut` e `Loop Over Items`
5. Usa **OpenAI (GPT-4o Mini)** para gerar variações da mensagem
6. Envia a mensagem via **HTTP Request** para uma API do WhatsApp
7. Espera entre 1 a 30 segundos usando um valor aleatório (evita bloqueio)
8. Registra o envio no **Microsoft Excel 365** com nome, número e cidade

---

## 🧠 Benefícios

- Evita bloqueios no WhatsApp por excesso de mensagens
- Usa inteligência artificial para personalização
- Totalmente escalável para 200+ contatos por campanha
- Automatiza toda a prospecção inicial com controle

---

## 🛠️ Requisitos

- N8N (self-hosted ou cloud)
- API de WhatsApp ativa (WPPConnect, WhatsApp Cloud API etc.)
- Conta OpenAI (GPT-4o mini configurado)
- Microsoft Excel 365 conectado
- Leads recebidos por webhook ou formulário

---

## 🧩 Nós utilizados no fluxo

| Nó                      | Função                                                                 |
|-------------------------|------------------------------------------------------------------------|
| **Webhook**             | Recebe os dados de entrada (números, nomes, mensagens, etc.)           |
| **Edit Fields**         | Cria arrays com números e nomes a partir dos dados brutos recebidos    |
| **Switch**              | Verifica o tipo de envio (`texto` ou `imagem`)                         |
| **Split Out**           | Separa os arrays em itens únicos                                       |
| **Loop Over Items**     | Executa um loop para envio individual                                  |
| **OpenAI**              | Gera variações criativas e humanizadas das mensagens                   |
| **HTTP Request**        | Envia a mensagem para a API do WhatsApp                                |
| **Code**                | Gera um número aleatório de 1 a 30 (tempo de espera em segundos)       |
| **Wait**                | Aguarda o tempo aleatório entre os envios                              |
| **Microsoft Excel 365** | Registra os envios feitos com número, nome e cidade                    |

---

## 🔁 Demonstração visual do fluxo

![Fluxo N8N - Disparador em Massa](![image](https://github.com/user-attachments/assets/aed7f127-7adc-4ac0-aa73-acecaa40243e)
)

---

## 📎 Download do Workflow

📥 [`Disparo em Massa.json`](./Disparo%20em%20Massa.json)

---

## 🧠 Exemplo da mensagem com IA

```text
Original: Olá, Claudio, temos uma novidade pra você sobre nosso serviço!
Gerado pela IA: Oi, Claudio! 🌟 Passando aqui pra te contar uma super novidade sobre o nosso serviço! 🚀
