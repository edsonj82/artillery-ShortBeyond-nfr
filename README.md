
# 📘 Testes de Performance com Artillery e Inteligência Artificial

Este projeto demonstra uma abordagem profissional para **testes de performance em APIs** utilizando **Artillery** aliado ao apoio de **Inteligência Artificial** para interpretação técnica dos relatórios gerados.

O objetivo é simular jornadas reais de usuários, avaliar o comportamento da API sob diferentes padrões de carga e extrair **insights acionáveis** a partir dos resultados.

---

## 🎯 Objetivos do Projeto

- Validar a estabilidade da API sob carga progressiva e picos repentinos
- Medir latência, throughput e taxa de erros em cenários reais
- Identificar gargalos em autenticação, validações e persistência em banco
- Utilizar IA para acelerar e qualificar a análise dos relatórios JSON
- Documentar um modelo replicável de testes de performance

---

## 🧱 Stack Utilizada

| Ferramenta | Finalidade |
|---|---|
| **Artillery** | Execução dos testes de carga |
| **Node.js** | Runtime para execução do Artillery |
| **CSV** | Massa de dados de usuários |
| **YAML** | Definição dos cenários |
| **JSON** | Relatórios gerados |
| **Inteligência Artificial** | Interpretação técnica dos resultados |

---

## ⚙️ Configuração do Ambiente para Execução com Artillery

### Instalar Node.js (18+)

```bash
node -v
```

Download: https://nodejs.org/

---

### Instalar Artillery globalmente

```bash
npm install -g artillery
```

Verificar:

```bash
artillery -V
```

Documentação oficial:  
https://www.artillery.io/docs

---

## ▶️ Como Executar os Testes

Executar cenários e gerar relatórios:

```bash
artillery run login.yaml --output login.json
artillery run pre-register.yaml --output pre-register.json
artillery run register.yaml --output register.json
artillery run spike.yaml --output spike.json
```

---

## 🔗 Comandos Úteis do Artillery

```bash
artillery run <cenario>.yaml --output <relatorio>.json
artillery report <relatorio>.json
BASE_URL=https://api.suaaplicacao.com artillery run login.yaml
artillery run login.yaml -o login.json -w 4
```

Referências oficiais:

- https://www.artillery.io/docs
- https://www.artillery.io/docs/reference/test-script
- https://www.artillery.io/docs/reference/data-sources
- https://www.artillery.io/docs/reference/reports

---

## 🗂️ Estrutura dos Arquivos

```
.
├── login.yaml
├── pre-register.yaml
├── register.yaml
├── spike.yaml
├── users.csv
├── login.json
├── pre-register.json
├── register.json
├── spike.json
└── README.md
```

---

## 👥 Massa de Dados

```csv
name,email,password
```

A massa é utilizada dinamicamente pelos cenários para simular usuários reais.

---

## 🧪 Cenários Implementados (Visão em Grade)

| Cenário | Objetivo | Fluxo Executado | O que o teste revela |
|---|---|---|---|
| 🔐 **Login** (`login.yaml`) | Validar autenticação sob carga | Credenciais → Token → Latência | Gargalos em autenticação e banco |
| 📝 **Pré-Cadastro** (`pre-register.yaml`) | Entrada massiva de usuários | Dados iniciais → Validações | Gargalos em regras de negócio |
| 🧾 **Cadastro Completo** (`register.yaml`) | Finalização de cadastro | Complemento → Persistência | Locks, escrita concorrente |
| ⚡ **Spike Test** (`spike.yaml`) | Pico abrupto de requisições | Aumento repentino de VUs | Resiliência e recuperação |

---

## 📊 Interpretação dos Relatórios (JSON)

| Campo | Significado |
|---|---|
| `latency.p95` | Tempo máximo para 95% das requisições |
| `latency.p99` | Limite extremo de lentidão |
| `errors` | Quantidade de falhas |
| `throughput` | Requisições por segundo |
| `scenariosCreated` | Total de execuções |

---

## 🧠 Uso de Inteligência Artificial na Análise

Os relatórios JSON foram analisados com apoio de IA para:

- Identificar padrões de degradação
- Interpretar grandes volumes de métricas rapidamente
- Sugerir possíveis causas técnicas de gargalos
- Apoiar decisões técnicas do time

Essa abordagem reduz drasticamente o tempo de análise manual.

---

## 🚀 Próximos Passos

- Incluir gráficos gerados a partir dos JSON
- Comparar execuções antes/depois de otimizações
- Integrar execução em pipeline CI/CD
- Criar dashboards contínuos

---

## 👨‍💻 Autor

**Edson José dos Santos**  
QA Automation & Performance Enthusiast