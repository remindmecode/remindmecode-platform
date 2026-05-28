# 🌿 Versionamento — Estratégia Git

> **Documento:** Estratégia Git  
> **Código:** DOC-GIT-001  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Definir a estratégia de versionamento e organização do repositório do REMINDMECODE, garantindo controle das mudanças, rastreabilidade da evolução da plataforma e estabilidade do desenvolvimento.

---

# 🧠 Contexto

O REMINDMECODE é desenvolvido de forma incremental, modular e evolutiva, exigindo uma estratégia de versionamento que permita:

* isolamento de mudanças;
* integração controlada;
* rastreabilidade técnica;
* segurança evolutiva;
* organização do desenvolvimento;
* suporte à colaboração futura.

A estratégia Git estabelece como funcionalidades, correções e documentos evoluem dentro do projeto.

---

# 🧩 Princípios da Estratégia

A estratégia de versionamento do projeto é baseada nos seguintes princípios:

---

## Isolamento de mudanças

Cada alteração deve ocorrer em uma branch específica, evitando impacto direto nas branches principais.

---

## Integração controlada

Mudanças somente são integradas após validação funcional e revisão estrutural.

---

## Clareza e rastreabilidade

Toda alteração deve possuir:

* escopo definido;
* identificação clara;
* histórico rastreável;
* vínculo com backlog ou issue.

---

## Evolução incremental

O sistema evolui de forma progressiva, permitindo entregas contínuas e organizadas.

---

## Segurança da base principal

As branches principais devem permanecer estáveis e utilizáveis.

---

# 🌳 Estrutura de Branches

O repositório utiliza organização baseada em branches com responsabilidades bem definidas.

---

## main

Representa a versão estável da plataforma.

### Características

* contém apenas código validado;
* representa versões consolidadas;
* deve permanecer estável;
* não recebe commits diretos.

---

## develop

Representa a linha principal de desenvolvimento contínuo.

### Características

* integra funcionalidades concluídas;
* serve como base para novas branches;
* concentra evolução incremental do projeto.

---

## feature/*

Utilizada para desenvolvimento de funcionalidades, documentos ou evoluções específicas.

### Origem

Criada a partir da `develop`.

---

### Exemplos

```text
feature/architecture-documentation
feature/project-management-documentation
feature/patient-module
feature/dashboard-indicators
```

---

## bugfix/*

Utilizada para correção de falhas identificadas durante desenvolvimento.

### Origem

Criada a partir da `develop`.

---

### Exemplos

```text
bugfix/login-validation
bugfix/persistence-error
bugfix/date-validation
```

---

## hotfix/*

Utilizada para correções urgentes em ambiente estável.

### Origem

Criada a partir da `main`.

---

### Características

Após conclusão:

* deve ser integrada em `main`;
* deve ser integrada em `develop`.

---

# 🔁 Fluxo de Desenvolvimento

## 1. Atualização da branch base

Antes de iniciar uma nova atividade:

```bash
git checkout develop
git pull origin develop
```

---

## 2. Criação da branch de trabalho

Criar branch específica para a atividade.

### Exemplo

```bash
git checkout -b feature/architecture-documentation
```

---

## 3. Desenvolvimento

Durante o desenvolvimento:

* implementar alterações;
* manter commits organizados;
* validar funcionamento;
* seguir padrões definidos do projeto.

---

## 4. Commit das alterações

Os commits devem:

* possuir escopo claro;
* seguir padrão definido;
* representar mudanças objetivas.

### Exemplo

```bash
git commit -m "📚 docs(architecture): create architecture overview document [DOC-ARC-001]"
```

---

## 5. Push da branch

Após evolução local:

```bash
git push origin feature/architecture-documentation
```

---

## 6. Pull Request

A integração ocorre via Pull Request para `develop`.

O PR deve permitir validação de:

* escopo;
* aderência arquitetural;
* organização;
* rastreabilidade;
* consistência estrutural.

---

## 7. Integração

Após validação:

* branch é integrada na `develop`;
* branch local e remota podem ser removidas.

---

# 🧾 Organização das Branches

Cada branch deve representar:

* uma funcionalidade;
* uma documentação;
* uma correção;
* uma melhoria específica.

---

## Não é permitido

* branches genéricas;
* múltiplos escopos misturados;
* alterações sem vínculo claro;
* branches sem objetivo definido.

---

# 🔒 Regras de Versionamento

## Não é permitido

* commit direto em `main`;
* commit direto em `develop` sem fluxo controlado;
* alterações fora de branch específica;
* mistura de funcionalidades distintas.

---

## É obrigatório

* utilizar branches dedicadas;
* seguir padrão de commits;
* manter histórico organizado;
* validar alterações antes da integração.

---

# 🔍 Rastreabilidade

Toda alteração deve permitir identificar:

* o que foi alterado;
* por que foi alterado;
* qual área foi impactada;
* qual issue ou backlog está relacionada.

A rastreabilidade ocorre através de:

* branches;
* commits;
* Pull Requests;
* códigos documentais;
* backlog do projeto.

---

# 🔗 Integração com Backlog

Toda branch deve estar associada a:

* issue;
* funcionalidade;
* documento;
* correção;
* melhoria específica.

---

## Exemplo

```text
[DOCS] Create architecture documentation #3
```

---

# 🧹 Limpeza de Branches

Após integração da branch:

---

## Remover branch local

```bash
git branch -d feature/architecture-documentation
```

---

## Remover branch remota

```bash
git push origin --delete feature/architecture-documentation
```

---

# 🚫 Práticas que Comprometem o Projeto

As seguintes práticas devem ser evitadas:

* commits grandes e desorganizados;
* ausência de padronização;
* integração sem validação;
* branches sem escopo;
* ausência de rastreabilidade;
* mistura de responsabilidades;
* alterações diretas na branch principal.

---

# 🚀 Evolução da Estratégia

A estratégia Git poderá evoluir conforme:

* crescimento da equipe;
* aumento da complexidade;
* maturidade do projeto;
* necessidade de pipelines automatizados;
* adoção de CI/CD;
* versionamento de releases.

---

# 🎯 Resultado Esperado

A aplicação desta estratégia garante que o REMINDMECODE evolua com:

* organização;
* previsibilidade;
* estabilidade;
* segurança;
* rastreabilidade;
* sustentabilidade evolutiva.

---