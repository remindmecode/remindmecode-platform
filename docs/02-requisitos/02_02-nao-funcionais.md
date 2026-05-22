# 📌 Requisitos Não Funcionais

> **Documento:** Requisitos Não Funcionais  
> **Código:** DOC-RNF-001  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-22  

---

# 🎯 Objetivo

Definir os atributos de qualidade, restrições técnicas e critérios arquiteturais da plataforma, garantindo segurança, desempenho, confiabilidade, escalabilidade e sustentabilidade evolutiva do sistema.

---

# 🧠 Contexto

Os requisitos não funcionais descrevem características técnicas e operacionais que influenciam diretamente:

- arquitetura da solução;
- experiência de uso;
- confiabilidade institucional;
- segurança da informação;
- capacidade evolutiva da plataforma;
- operação em ambiente hospitalar.

Esses requisitos servirão como base para decisões arquiteturais, infraestrutura, desenvolvimento e governança tecnológica.

---

# 🔐 Categoria: Segurança

## RNF-SEG-001 — Criptografia de Senhas

**Descrição:**
A plataforma deve armazenar senhas utilizando algoritmos seguros de hash criptográfico.

**Prioridade:**
Alta

---

## RNF-SEG-002 — Autenticação Segura

**Descrição:**
A plataforma deve garantir autenticação segura de usuários através de mecanismos protegidos contra acesso não autorizado.

**Prioridade:**
Alta

---

## RNF-SEG-003 — Controle de Sessão

**Descrição:**
A plataforma deve encerrar sessões autenticadas após período de inatividade configurável.

**Prioridade:**
Média

---

## RNF-SEG-004 — Controle de Acesso

**Descrição:**
A plataforma deve restringir funcionalidades conforme perfil e permissões do usuário autenticado.

**Prioridade:**
Alta

---

# ⚡ Categoria: Desempenho

## RNF-DSP-001 — Tempo de Resposta

**Descrição:**
A plataforma deve responder operações comuns em tempo adequado para uso operacional institucional.

**Referência inicial:**
Até 2 segundos em operações de consulta padrão.

**Prioridade:**
Alta

---

## RNF-DSP-002 — Processamento Analítico

**Descrição:**
A plataforma deve suportar processamento de indicadores e consolidações analíticas sem comprometer estabilidade operacional.

**Prioridade:**
Alta

---

# 📈 Categoria: Escalabilidade

## RNF-ESC-001 — Crescimento Progressivo

**Descrição:**
A plataforma deve permitir crescimento progressivo de usuários, módulos e volume de dados sem necessidade de reestruturação completa da solução.

**Prioridade:**
Alta

---

## RNF-ESC-002 — Arquitetura Modular

**Descrição:**
A arquitetura da plataforma deve permitir evolução incremental de funcionalidades e serviços institucionais.

**Prioridade:**
Alta

---

# 🛡️ Categoria: Confiabilidade

## RNF-CON-001 — Integridade de Dados

**Descrição:**
A plataforma deve garantir integridade e consistência das informações institucionais armazenadas.

**Prioridade:**
Alta

---

## RNF-CON-002 — Persistência de Dados

**Descrição:**
A plataforma deve preservar histórico operacional e rastreabilidade institucional dos registros.

**Prioridade:**
Alta

---

# 📊 Categoria: Disponibilidade

## RNF-DSPB-001 — Disponibilidade Operacional

**Descrição:**
A plataforma deve possuir disponibilidade adequada para utilização contínua nos setores institucionais.

**Prioridade:**
Alta

---

# 🔎 Categoria: Observabilidade e Auditoria

## RNF-OBS-001 — Registro de Logs

**Descrição:**
A plataforma deve registrar eventos operacionais relevantes para análise, auditoria e rastreabilidade.

**Prioridade:**
Alta

---

## RNF-OBS-002 — Auditoria de Operações

**Descrição:**
A plataforma deve permitir identificação de alterações realizadas nos dados institucionais.

**Prioridade:**
Alta

---

# 🧩 Categoria: Manutenibilidade

## RNF-MNT-001 — Separação em Camadas

**Descrição:**
A plataforma deve ser estruturada em camadas arquiteturais bem definidas.

**Prioridade:**
Alta

---

## RNF-MNT-002 — Padronização de Código

**Descrição:**
A plataforma deve seguir padrões de organização, nomenclatura e versionamento definidos pela equipe de desenvolvimento.

**Prioridade:**
Média

---

# 🔄 Evolução dos Requisitos

Os requisitos não funcionais poderão evoluir conforme:

* crescimento institucional;
* aumento de carga operacional;
* evolução tecnológica da plataforma;
* maturidade analítica institucional;
* necessidade de integração entre sistemas.

A rastreabilidade e versionamento dos requisitos deverão ser mantidos durante todo o ciclo evolutivo do sistema.


