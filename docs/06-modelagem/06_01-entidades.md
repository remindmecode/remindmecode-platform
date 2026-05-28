# 🧱 Modelagem — Modelo de Entidades

> **Documento:** Modelo de Entidades  
> **Código:** DOC-MOD-001  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Definir as principais entidades do REMINDMECODE, estabelecendo a base estrutural do domínio institucional, da persistência de dados e da futura modelagem relacional da plataforma.

---

# 🧠 Contexto

O modelo de entidades representa a estrutura central de dados da plataforma.

As entidades descritas neste documento:

* representam conceitos persistentes do domínio;
* sustentam os fluxos operacionais;
* permitem rastreabilidade institucional;
* viabilizam geração de indicadores;
* estruturam a camada analítica;
* servem de base para diagramas e banco de dados.

O modelo é orientado à trajetória institucional do paciente e à produção contínua de dados assistenciais, operacionais e administrativos.

---

# 🧩 Princípios de Modelagem

# Centralidade da trajetória do paciente

A modelagem é orientada ao percurso institucional do paciente ao longo do cuidado.

---

# Separação entre domínio e interface

As entidades representam dados persistidos e regras estruturais do domínio, independentemente de telas ou fluxos visuais.

---

# Reutilização de informação

Entidades podem ser utilizadas por múltiplos módulos e processos institucionais.

---

# Evolução incremental

Novas entidades poderão ser incorporadas progressivamente sem necessidade de reconstrução estrutural completa.

---

# Orientação temporal

Grande parte das entidades possui natureza temporal e orientada a eventos.

---

# Rastreabilidade institucional

O modelo prioriza rastreamento de:

* origem do dado;
* evolução;
* contexto operacional;
* histórico institucional.

---

# 🧱 Classificação das Entidades

As entidades do sistema podem ser agrupadas conforme sua natureza funcional e estrutural.

---

# 🟦 Entidades Estruturais

Representam elementos organizacionais e de configuração institucional.

## Exemplos

* usuario
* perfil_acesso
* permissao
* configuracao_sistema
* setor
* tipo_setor
* leito
* convenio

---

# 🟨 Entidades Assistenciais Centrais

Representam o núcleo da trajetória assistencial do paciente.

## Exemplos

* paciente
* atendimento
* internacao
* observacao
* movimentacao

Essas entidades estruturam o fluxo assistencial principal da plataforma.

---

# 🟧 Entidades Operacionais Assistenciais

Representam registros produzidos durante o cuidado e operação institucional.

## Exemplos

* registro_assistencial
* escala_assistencial
* classificacao_risco
* uso_dispositivo
* evolucao_clinica
* evento_assistencial

---

# 🟥 Entidades de Qualidade e Segurança

Representam monitoramento institucional, eventos e vigilância.

## Exemplos

* evento
* tipo_evento
* classificacao_evento
* investigacao_evento
* registro_infeccao
* microbiologia
* material_coletado

---

# 🟪 Entidades Analíticas e Indicadores

Representam estruturas utilizadas para consolidação institucional e inteligência operacional.

## Exemplos

* indicador
* resultado_indicador
* relatorio
* snapshot_indicador

---

# 🟩 Entidades Administrativas e Financeiras

Representam componentes administrativos e financeiros relacionados ao ciclo assistencial.

## Exemplos

* autorizacao
* faturamento
* glosa
* recebimento
* conta_hospitalar

---

# 🟫 Entidades de Experiência e Relacionamento

Representam interação institucional e experiência do paciente.

## Exemplos

* pesquisa_satisfacao
* manifestacao
* reclamacao
* elogio

---

# 🔗 Entidades Transversais

Algumas entidades possuem natureza transversal e são reutilizadas em múltiplos contextos institucionais.

## Principais entidades transversais

* paciente
* setor
* usuario
* atendimento
* internacao
* evento
* indicador

Essas entidades possuem alto potencial de reutilização e forte impacto arquitetural.

---

# ⏱️ Entidades Orientadas a Tempo

Determinadas entidades possuem comportamento temporal explícito.

## Exemplos

* atendimento
* internacao
* movimentacao
* uso_dispositivo
* observacao
* evento
* classificacao_risco

Essas entidades são fundamentais para:

* indicadores;
* rastreabilidade;
* análise operacional;
* analytics institucional.

---

# 🧠 Entidades Derivadas

Algumas informações relevantes não serão persistidas diretamente, sendo derivadas de cálculos, regras ou combinações de dados.

## Exemplos

* tempo de permanência;
* tempo de espera;
* taxa de ocupação;
* permanência por setor;
* indicadores de produtividade;
* score operacional;
* métricas analíticas.

Essas estruturas pertencem principalmente à camada analítica da plataforma.

---

# 📦 Entidades Prioritárias para Primeira Fase

As primeiras entidades previstas para modelagem detalhada são:

| Categoria    | Entidades                         |
| ------------ | --------------------------------- |
| Estrutural   | usuario, setor, leito, convenio   |
| Assistencial | paciente, atendimento, internacao |
| Operacional  | movimentacao, uso_dispositivo     |
| Analítica    | indicador                         |
| Segurança    | evento                            |

---

# 🔄 Evolução da Modelagem

A modelagem poderá evoluir conforme:

* crescimento dos módulos;
* amadurecimento institucional;
* necessidade analítica;
* expansão operacional;
* novas integrações.

Mudanças devem priorizar:

* baixo acoplamento;
* reutilização;
* rastreabilidade;
* integridade dos dados;
* escalabilidade.

---

# 🚀 Resultado Esperado

A definição consistente das entidades permite que o REMINDMECODE evolua com:

* base estrutural sólida;
* modelagem sustentável;
* rastreabilidade institucional;
* integração entre módulos;
* reutilização de informação;
* capacidade analítica futura.

---
