# 🧾 Padrões — Commits Semânticos

> **Documento:** Padrões de Commits Semânticos  
> **Código:** DOC-PTN-001  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-28  

---

# 🎯 Objetivo

Definir o padrão oficial de commits do projeto, garantindo:

* rastreabilidade;
* organização do histórico;
* padronização colaborativa;
* clareza evolutiva;
* alinhamento com Conventional Commits e GitFlow.

---

# 🧠 Contexto

O projeto utiliza:

* **Conventional Commits** para semântica;
* **Gitmoji** para categorização visual;
* **GitFlow** para organização das branches;
* padronização incremental da documentação e arquitetura.

O objetivo é manter um histórico limpo, compreensível e consistente ao longo da evolução da plataforma.

---

# 📌 Estrutura do Commit

## Formato Oficial

```text
<gitmoji> <type>(<scope>): <description> [<reference>]
```

---

## Estrutura dos Elementos

| Elemento    | Descrição                                |
| ----------- | ---------------------------------------- |
| gitmoji     | Categoria visual do commit               |
| type        | Tipo semântico da alteração              |
| scope       | Área afetada                             |
| description | Descrição resumida                       |
| reference   | Documento, issue ou contexto relacionado |

---

# 🧩 Tipos Semânticos

| Tipo         | Descrição                           |
| ------------ | ----------------------------------- |
| feat         | Nova funcionalidade                 |
| fix          | Correção de bug                     |
| docs         | Documentação                        |
| style        | Formatação sem alteração lógica     |
| refactor     | Refatoração sem mudança funcional   |
| perf         | Otimização de performance           |
| test         | Testes automatizados                |
| chore        | Tarefas de manutenção               |
| build        | Build, dependências e empacotamento |
| ci           | Integração contínua                 |
| infra        | Infraestrutura e configuração       |
| architecture | Alterações arquiteturais            |

---

# 😀 Gitmojis Utilizados

| Gitmoji | Uso                 |
| ------- | ------------------- |
| 📚      | Documentação        |
| ✨       | Nova funcionalidade |
| 🐛      | Correção de bug     |
| ♻️      | Refatoração         |
| ⚡       | Performance         |
| 🔧      | Configuração        |
| 🚀      | Deploy / release    |
| ✅       | Testes              |
| 🏗️     | Arquitetura         |
| 🔥      | Remoção             |
| 🚑      | Hotfix crítico      |

---

# ✍️ Regras de Escrita

## Idioma

* commits em inglês;
* documentação pode permanecer em português;
* nomes técnicos seguem convenções da tecnologia utilizada.

---

## Escrita

### Utilizar verbo no imperativo

✔ create
✔ add
✔ update
✔ remove
✔ refactor
✔ configure

❌ created
❌ adding
❌ fixed

---

## Recomendações

* descrição curta e objetiva;
* evitar frases longas;
* evitar pontuação final;
* máximo recomendado de 72 caracteres;
* manter consistência semântica.

---

# 📚 Escopos Recomendados

| Scope        | Contexto       |
| ------------ | -------------- |
| docs         | Documentação   |
| architecture | Arquitetura    |
| management   | Gestão         |
| requirements | Requisitos     |
| uml          | Diagramas UML  |
| backend      | Backend        |
| frontend     | Frontend       |
| database     | Banco de dados |
| infra        | Infraestrutura |
| analytics    | Analytics      |
| security     | Segurança      |

---

# 🎯 Exemplos Oficiais

## Documentação

```bash
git commit -m "📚 docs(requirements): create business rules document [DOC-RN-001]"
```

```bash
git commit -m "📚 docs(architecture): create architecture overview document [DOC-ARC-001]"
```

---

## Funcionalidade

```bash
git commit -m "✨ feat(auth): implement user authentication"
```

---

## Correção

```bash
git commit -m "🐛 fix(login): resolve token validation issue"
```

---

## Refatoração

```bash
git commit -m "♻️ refactor(service): simplify patient flow logic"
```

---

## Infraestrutura

```bash
git commit -m "🔧 infra(gitflow): configure branching strategy"
```

---

# 🌿 Estratégia de Branches

O projeto segue organização baseada em GitFlow.

---

## Branches Principais

| Branch  | Objetivo                 |
| ------- | ------------------------ |
| main    | Produção                 |
| develop | Desenvolvimento contínuo |

---

## Branches de Trabalho

| Prefixo   | Uso                            |
| ----------| ------------------------------ |
| feature/  | Funcionalidades e documentação |
| fix/      | Correções                      |
| refactor/ | Refatorações                   |
| hotfix/   | Correções críticas             |
| release/  | Preparação de release          |

---

# 🔄 Fluxo Básico de Trabalho

## Atualizar Branch Local

```bash
git checkout develop
git pull origin develop
```

---

## Criar Nova Branch

```bash
git checkout -b feature/project-management-documentation
```

---

## Enviar Branch Remota

```bash
git push origin feature/project-management-documentation
```

---

## Abrir Pull Request

O Pull Request deve:

* possuir título padronizado;
* referenciar a issue relacionada;
* utilizar labels apropriadas;
* seguir o escopo da branch.

---

# 🧹 Operações Auxiliares

## Remover último commit mantendo alterações staged

```bash
git reset --soft HEAD~1
```

---

## Remover último commit mantendo alterações unstaged

```bash
git reset HEAD~1
```

---

## Remover último commit permanentemente

```bash
git reset --hard HEAD~1
```

⚠️ Utilizar com cautela.

---

## Remover branch local

```bash
git branch -d feature/requirements-documentation
```

---

## Remover branch remota

```bash
git push origin --delete feature/requirements-documentation
```

---

# 🚀 Fluxo de Release e Merge para Main

O merge da branch `develop` para `main` representa a promoção de uma baseline estável do projeto.

Esse processo deve ocorrer apenas quando:

* funcionalidades estiverem consolidadas;
* documentação estiver validada;
* pipeline estiver consistente;
* milestone estiver concluída.

---

## 🔄 Atualizar branch develop

```bash
git checkout develop
git pull origin develop
```

---

## 🔄 Atualizar branch main

```bash
git checkout main
git pull origin main
```

---

## 🔀 Realizar merge da develop

```bash
git merge develop
```

---

## 🚀 Enviar atualização para repositório remoto

```bash
git push origin main
```

---

## 🏷️ Criar tag da release

```bash
git tag -a v0.1.0 -m "Initial documentation baseline"
```

---

## ☁️ Enviar tag para o remoto

```bash
git push origin v0.1.0
```

---

# 📌 Objetivos do processo

Esse fluxo garante:

* rastreabilidade de releases;
* estabilidade da branch principal;
* versionamento incremental;
* organização da evolução do projeto;
* criação de baselines técnicas confiáveis.

---

# ⚠️ Regras Importantes

* não realizar commits diretos na `main`;
* somente promover versões validadas;
* manter `develop` como base de integração contínua;
* criar tags para releases relevantes;
* preservar histórico limpo e rastreável.

---

# 🚀 Objetivos da Padronização

A padronização dos commits busca:

* melhorar rastreabilidade;
* facilitar manutenção;
* organizar evolução do projeto;
* apoiar versionamento semântico;
* simplificar auditoria técnica;
* melhorar colaboração;
* estruturar histórico evolutivo da plataforma;
* apoiar organização por milestones e releases.

---