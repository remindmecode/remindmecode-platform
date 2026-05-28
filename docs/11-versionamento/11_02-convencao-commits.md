# 📝 Versionamento — Convenção de Commits

> **Documento:** Convenção de Commits  
> **Código:** DOC-GIT-002  
> **Versão:** 1.0.  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Estabelecer como os commits são utilizados no fluxo de desenvolvimento do REMINDMECODE, garantindo organização, rastreabilidade, clareza histórica e alinhamento com o processo de engenharia da plataforma.

---

# 🧠 Contexto

Os commits representam a unidade básica de evolução do projeto.

Cada commit registra uma alteração específica realizada na plataforma, permitindo:

* rastrear mudanças;
* compreender evolução do sistema;
* identificar responsabilidades;
* apoiar revisões;
* facilitar manutenção;
* integrar desenvolvimento ao backlog do projeto.

A convenção de commits complementa a estratégia Git e os padrões definidos para o versionamento do sistema.

---

# 🔗 Relação com os Padrões do Projeto

O padrão estrutural de commits é definido em:

```text id="1a1q1s"
docs/08-padroes/commit-pattern.md
```

Este documento define como a convenção é aplicada operacionalmente dentro do fluxo do REMINDMECODE.

---

# 🧩 Papel dos Commits no Projeto

Os commits são utilizados para registrar:

* evolução de funcionalidades;
* correções de falhas;
* criação de documentação;
* ajustes estruturais;
* melhorias técnicas;
* alterações arquiteturais;
* organização do projeto.

Cada commit deve representar uma mudança lógica, objetiva e rastreável.

---

# 🌿 Relação com Branches

Os commits devem ser coerentes com o contexto da branch utilizada.

---

## feature/*

Commits representam evolução incremental de funcionalidades, documentos ou módulos.

### Exemplos

* criação de endpoints;
* implementação de fluxos;
* criação de documentação;
* evolução arquitetural.

---

## bugfix/*

Commits representam correções específicas de comportamento ou falhas técnicas.

### Exemplos

* correção de validação;
* ajuste de persistência;
* tratamento de erro.

---

## hotfix/*

Commits representam correções críticas e urgentes.

### Características

* mudanças objetivas;
* escopo reduzido;
* foco em estabilização.

---

## develop

A branch `develop` concentra integração de alterações já validadas.

Ela não deve ser utilizada para desenvolvimento desorganizado ou alterações sem controle.

---

## main

A branch `main` representa estado estável da plataforma.

Ela recebe apenas alterações já consolidadas e aprovadas.

---

# 📦 Granularidade dos Commits

## Princípio central

Um commit deve representar uma única mudança lógica.

---

## Diretrizes

Os commits devem:

* possuir objetivo claro;
* representar alteração específica;
* evitar múltiplas responsabilidades;
* preservar legibilidade histórica.

---

## Exemplos adequados

* criação de endpoint;
* ajuste de validação;
* criação de documento;
* correção de fluxo;
* melhoria de estrutura.

---

## Exemplos inadequados

* múltiplas funcionalidades no mesmo commit;
* mistura de refatoração e feature;
* alterações não relacionadas agrupadas;
* commits genéricos sem contexto.

---

# 🔁 Frequência de Commits

Os commits devem ocorrer de forma frequente e incremental.

---

## Objetivos

* preservar contexto;
* facilitar revisão;
* reduzir risco de perda;
* melhorar rastreabilidade;
* simplificar integração.

---

## Evitar

* longos períodos sem commit;
* commits gigantes;
* alterações acumuladas sem versionamento.

---

# 🔤 Estrutura dos Commits

O projeto utiliza:

* Conventional Commits;
* Gitmoji;
* escopo contextual;
* identificação documental quando aplicável.

---

## Estrutura adotada

```text id="n6m8dy"
<gitmoji> <type>(<scope>): <description> [<document-code>]
```

---

## Exemplo

```bash id="lxk4n7"
git commit -m "📚 docs(architecture): create architecture overview document [DOC-ARC-001]"
```

---

# 🧾 Tipos de Commit Utilizados

| Tipo     | Finalidade                         |
| -------- | ---------------------------------- |
| feat     | Nova funcionalidade                |
| fix      | Correção de falha                  |
| docs     | Documentação                       |
| refactor | Refatoração                        |
| style    | Ajustes de formatação              |
| perf     | Melhoria de performance            |
| test     | Criação ou ajuste de testes        |
| chore    | Manutenção e tarefas auxiliares    |
| build    | Configuração de build/dependências |
| ci       | Integração contínua e pipelines    |

---

# 📚 Gitmojis Utilizados no Projeto

| Gitmoji | Contexto            |
| ------- | ------------------- |
| 📚      | Documentação        |
| ✨       | Nova funcionalidade |
| 🐛      | Correção de bug     |
| ♻️      | Refatoração         |
| ⚡       | Performance         |
| ✅       | Testes              |
| 🔧      | Configuração        |
| 🚀      | Deploy ou release   |

---

# 🔗 Relação com Backlog e Issues

Todo commit deve possuir vínculo com:

* issue;
* funcionalidade;
* documento;
* correção;
* atividade planejada.

---

## Objetivo

Garantir:

* rastreabilidade;
* organização;
* alinhamento com planejamento;
* histórico compreensível.

---

# 🔍 Rastreabilidade

Os commits devem permitir identificar:

* o que foi alterado;
* qual contexto motivou a alteração;
* qual área foi impactada;
* qual atividade está relacionada.

A rastreabilidade ocorre através da combinação entre:

* branch;
* commit;
* Pull Request;
* issue;
* backlog;
* documentação.

---

# ⚙️ Relação com Qualidade

Os commits fazem parte do fluxo de qualidade da plataforma.

Antes da integração, as alterações devem:

* respeitar Definition of Done;
* seguir padrões arquiteturais;
* atender estratégia de testes;
* manter consistência estrutural.

---

# 🧠 Boas Práticas

---

## Recomendações

* manter commits pequenos e objetivos;
* revisar alterações antes do commit;
* escrever mensagens claras;
* preservar coerência histórica;
* separar responsabilidades;
* evitar commits temporários desnecessários.

---

## Recomendações para documentação

Para documentos do projeto, utilizar:

```bash id="r5d5p1"
📚 docs(scope): description [DOC-XXX-001]
```

---

# 🚫 Práticas Não Permitidas

Não devem ocorrer:

* commits genéricos;
* mensagens sem contexto;
* mistura de responsabilidades;
* commits sem vínculo com atividade;
* alterações não revisadas;
* versionamento desorganizado.

---

# 🚀 Evolução da Convenção

A convenção poderá evoluir conforme:

* crescimento do projeto;
* maturidade da equipe;
* adoção de automações;
* pipelines CI/CD;
* necessidade de auditoria técnica mais avançada.

---

# 🎯 Resultado Esperado

A aplicação desta convenção garante que o REMINDMECODE evolua com:

* histórico organizado;
* rastreabilidade clara;
* integração segura;
* alinhamento entre backlog e desenvolvimento;
* previsibilidade evolutiva;
* sustentabilidade técnica do projeto.

---