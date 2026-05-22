# 📌 Caso de Uso Detalhado — Visualizar Dashboard Operacional

> **Documento:** Caso de Uso Detalhado  
> **Código:** DOC-UC-003  
> **Caso de Uso:** UC-GST-001  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-22

---

# 🎯 Objetivo

Descrever o fluxo operacional responsável pela visualização de dashboards institucionais consolidados para monitoramento da operação hospitalar e suporte à tomada de decisão.

---

# 🧠 Contexto

Os dashboards operacionais representam a principal camada de visualização analítica da plataforma, permitindo que gestores acompanhem indicadores institucionais, comportamento operacional e eventos críticos em tempo contínuo.

A consolidação dessas informações busca ampliar a capacidade de monitoramento institucional e apoiar decisões baseadas em dados.

---

# 🧾 Identificação

| Campo | Valor |
|---|---|
| Caso de Uso | UC-GST-001 |
| Nome | Visualizar Dashboard Operacional |
| Domínio | Gestão Operacional |
| Módulo | Dashboards Institucionais |
| Ator Principal | Gestor |
| Prioridade | Alta |
| Complexidade | Média |
| Status | Em elaboração |

---

# 🎭 Atores Envolvidos

| Ator | Responsabilidade |
|---|---|
| Gestor | Monitorar indicadores e operação institucional |
| Plataforma | Consolidar, processar e apresentar informações analíticas |

---

# ✅ Pré-Condições

- usuário autenticado;
- usuário com permissão gerencial;
- indicadores previamente consolidados;
- dados institucionais disponíveis para análise.

---

# 🚀 Fluxo Principal

| Passo | Ação |
|---|---|
| 1 | Gestor acessa módulo de dashboards |
| 2 | Plataforma carrega indicadores institucionais consolidados |
| 3 | Plataforma apresenta visão operacional integrada |
| 4 | Gestor visualiza métricas operacionais e assistenciais |
| 5 | Gestor aplica filtros analíticos |
| 6 | Plataforma atualiza visualizações conforme filtros aplicados |
| 7 | Gestor analisa comportamento operacional |
| 8 | Plataforma mantém atualização das informações apresentadas |

---

# ⚠️ Fluxos Alternativos

## FA-01 — Aplicação de filtros analíticos

| Passo | Ação |
|---|---|
| 1 | Gestor seleciona critérios de análise |
| 2 | Plataforma processa filtros institucionais |
| 3 | Dashboard é atualizado dinamicamente |

---

## FA-02 — Ausência de dados consolidados

| Passo | Ação |
|---|---|
| 1 | Plataforma identifica ausência de informações |
| 2 | Plataforma apresenta alerta informativo |
| 3 | Dashboard permanece disponível sem indicadores consolidados |

---

# ❌ Fluxos de Exceção

## FE-01 — Falha de processamento analítico

| Passo | Ação |
|---|---|
| 1 | Plataforma identifica erro interno |
| 2 | Dashboard não é carregado corretamente |
| 3 | Evento é registrado em log operacional |
| 4 | Usuário é notificado sobre indisponibilidade temporária |

---

# 📌 Pós-Condições

- indicadores operacionais visualizados;
- informações institucionais analisadas;
- filtros analíticos aplicados;
- sessão de monitoramento registrada para auditoria.

---

# 🔐 Regras Relacionadas

| Regra | Descrição |
|---|---|
| RN-GST-001 | Apenas usuários autorizados podem acessar dashboards |
| RN-GST-002 | Indicadores devem utilizar dados consolidados |
| RN-GST-003 | Informações devem respeitar permissões institucionais |
| RN-GST-004 | Visualizações devem considerar filtros operacionais ativos |

---

# 📎 Requisitos Relacionados

| Requisito | Descrição |
|---|---|
| RF-GST-001 | Visualização de dashboard operacional |
| RF-GST-002 | Monitoramento de indicadores |
| RF-GST-003 | Consulta de indicadores por período |
| RF-ANL-002 | Aplicação de filtros analíticos |

---

# 🔄 Observações

Este caso de uso representa a visão inicial do monitoramento operacional institucional e poderá evoluir conforme expansão das capacidades analíticas, dashboards especializados e mecanismos avançados de inteligência institucional.