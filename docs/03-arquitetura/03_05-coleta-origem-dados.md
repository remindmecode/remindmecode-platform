# 🧩 Arquitetura de Coleta e Origem de Dados

> **Documento:** Arquitetura de Coleta e Origem de Dados  
> **Código:** DOC-ARC-005  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-26  

---

# 🎯 Objetivo

Definir a arquitetura conceitual de coleta, geração, consolidação e reutilização dos dados institucionais da plataforma, estabelecendo diretrizes para organização das informações operacionais, assistenciais e analíticas.

---

# 🧠 Contexto

A plataforma é concebida como uma solução orientada a dados institucionais, permitindo transformar registros operacionais em informações estruturadas para:

* acompanhamento assistencial;
* monitoramento operacional;
* geração de indicadores;
* auditoria institucional;
* rastreabilidade;
* suporte à tomada de decisão;
* evolução analítica da solução.

Diferentemente de sistemas tradicionais centrados apenas em telas ou formulários, a plataforma compreende os dados como elementos dinâmicos, reutilizáveis e evolutivos ao longo da jornada institucional do paciente.

---

# 🧩 Princípios da Coleta Institucional

## 🔄 Coleta distribuída

A geração de dados ocorre em múltiplos pontos institucionais, setores e momentos operacionais.

---

## ♻️ Reutilização da informação

Os dados devem ser coletados preferencialmente uma única vez e reutilizados em múltiplos contextos operacionais e analíticos.

---

## 🧠 Orientação a eventos

A plataforma deve compreender o fluxo institucional como uma sequência de eventos operacionais e assistenciais relacionados.

---

## 📈 Evolução progressiva

A arquitetura deve permitir expansão incremental da modelagem, dos fluxos e das integrações institucionais.

---

## 🛡️ Rastreabilidade

Todo dado institucional poderá possuir contexto de origem, autoria, temporalidade e histórico de alterações.

---

# 🔄 Ciclo de Vida do Dado Institucional

Os dados institucionais percorrem múltiplas etapas dentro da plataforma:

* geração;
* validação;
* complementação;
* atualização;
* consolidação;
* reutilização;
* análise;
* auditoria;
* armazenamento histórico.

Esse ciclo permite que uma mesma informação seja utilizada simultaneamente em contextos assistenciais, operacionais, administrativos e analíticos.

---

# 🧠 Conceitos Fundamentais

## 📌 Dado Primário

Informação originalmente registrada em determinado ponto operacional.

### Exemplos

* data/hora de entrada;
* setor;
* leito;
* classificação de risco;
* dispositivo utilizado.

---

## 📌 Dado Complementar

Informação que complementa ou detalha registros já existentes.

### Exemplos

* hipótese diagnóstica;
* motivo da internação;
* especialidade;
* desfecho clínico.

---

## 📌 Dado Derivado

Informação obtida a partir de cálculos, regras ou interpretações de outros dados.

### Exemplos

* tempo de permanência;
* taxa de ocupação;
* tempo porta-atendimento;
* média institucional;
* classificação por score.

---

## 📌 Dado Reutilizável

Informação que pode ser compartilhada entre múltiplos módulos, relatórios ou indicadores.

### Exemplos

* identificação institucional;
* setor;
* tipo de atendimento;
* convênio;
* datas assistenciais;
* movimentações internas.

---

# 🧩 Arquitetura dos Pontos de Coleta

Os pontos de coleta não devem ser compreendidos apenas como telas, formulários ou planilhas, mas como momentos institucionais de geração ou atualização da informação.

Cada ponto de coleta poderá envolver:

* setores institucionais;
* profissionais assistenciais;
* processos administrativos;
* registros eletrônicos;
* registros manuais;
* eventos operacionais;
* atualizações evolutivas.

A arquitetura considera que os dados podem:

* nascer em diferentes contextos;
* ser complementados posteriormente;
* sofrer atualização temporal;
* alimentar múltiplos fluxos analíticos;
* possuir dependência contextual e histórica.

---

# 🧭 Jornada Institucional da Informação

Ao longo da trajetória institucional do paciente, os dados percorrem múltiplos fluxos operacionais.

Os principais macro pontos de coleta são apresentados a seguir.

---

# 📥 Ponto de Coleta 1 — Entrada e Admissão

## Contextos Relacionados

* pronto-socorro;
* internação eletiva;
* admissão obstétrica;
* retorno programado;
* transferência institucional.

## Exemplos de Dados

* identificação do paciente;
* data/hora de entrada;
* origem do paciente;
* tipo de atendimento;
* convênio;
* unidade de admissão.

## Características

* dados predominantemente primários;
* altamente reutilizáveis;
* fundamentais para rastreabilidade institucional.

---

# 🩺 Ponto de Coleta 2 — Triagem e Classificação Inicial

## Exemplos de Dados

* classificação de risco;
* sinais iniciais;
* prioridade assistencial;
* queixa principal;
* responsável pelo registro.

## Potencial Analítico

* tempo porta-atendimento;
* perfil assistencial;
* gravidade operacional;
* monitoramento de fluxo.

---

# 🏥 Ponto de Coleta 3 — Atendimento e Conduta Assistencial

## Exemplos de Dados

* especialidade;
* hipótese diagnóstica;
* conduta clínica;
* solicitação de exames;
* necessidade de internação;
* encaminhamentos.

## Características

* dados fortemente conectados à trajetória futura do paciente;
* relevantes para produção institucional e analytics.

---

# 🛏️ Ponto de Coleta 4 — Observação e Permanência Assistencial

## Exemplos de Dados

* permanência em observação;
* monitoramento clínico;
* evolução assistencial;
* exames realizados;
* destino após observação.

## Potencial Analítico

* tempo de permanência;
* ocupação operacional;
* resolutividade assistencial.

---

# 🏨 Ponto de Coleta 5 — Internação Hospitalar

## Exemplos de Dados

* setor de internação;
* leito;
* clínica;
* médico responsável;
* origem da internação;
* classificação assistencial.

## Características

* dados estruturantes;
* altamente reutilizáveis;
* fundamentais para indicadores institucionais.

---

# 📋 Ponto de Coleta 6 — Acompanhamento Assistencial

## Exemplos de Dados

* evolução clínica;
* escalas assistenciais;
* risco assistencial;
* uso de dispositivos;
* cuidados realizados;
* intercorrências.

## Potencial Analítico

* dimensionamento assistencial;
* produtividade;
* perfil assistencial;
* qualidade do cuidado.

---

# 🚨 Ponto de Coleta 7 — Unidade Crítica e UTI

## Exemplos de Dados

* gravidade clínica;
* ventilação mecânica;
* drogas vasoativas;
* dispositivos invasivos;
* permanência em UTI;
* scores clínicos.

## Potencial Analítico

* mortalidade;
* gravidade institucional;
* uso de recursos críticos;
* indicadores assistenciais.

---

# 🧪 Ponto de Coleta 8 — Dispositivos e Bundles

## Exemplos de Dados

* tipo de dispositivo;
* data de inserção;
* data de retirada;
* conformidade assistencial;
* manutenção do dispositivo.

## Potencial Analítico

* segurança do paciente;
* indicadores de infecção;
* bundles assistenciais;
* auditoria institucional.

---

# 🏥 Ponto de Coleta 9 — Procedimentos e Centro Cirúrgico

## Exemplos de Dados

* procedimento realizado;
* sala cirúrgica;
* cancelamentos;
* especialidade;
* intercorrências;
* desfecho do procedimento.

---

# ⚠️ Ponto de Coleta 10 — Qualidade e Eventos Adversos

## Exemplos de Dados

* ocorrência assistencial;
* classificação do evento;
* dano associado;
* investigação;
* ações corretivas.

## Potencial Analítico

* segurança do paciente;
* qualidade assistencial;
* melhoria contínua;
* governança institucional.

---

# 🦠 Ponto de Coleta 11 — Vigilância e CCIH

## Exemplos de Dados

* culturas;
* microorganismos;
* vínculos com dispositivos;
* suspeitas infecciosas;
* confirmações laboratoriais.

## Potencial Analítico

* vigilância epidemiológica;
* indicadores infecciosos;
* rastreabilidade assistencial.

---

# 🔄 Ponto de Coleta 12 — Movimentações Internas

## Exemplos de Dados

* transferências;
* mudança de leito;
* mudança de setor;
* origem e destino;
* motivo da movimentação.

## Potencial Analítico

* ocupação;
* gestão de leitos;
* análise de fluxo;
* permanência institucional.

---

# 🏁 Ponto de Coleta 13 — Alta, Transferência e Desfecho

## Exemplos de Dados

* tipo de saída;
* data/hora da alta;
* óbito;
* transferência;
* evasão;
* encerramento institucional.

## Potencial Analítico

* mortalidade;
* tempo de permanência;
* produção institucional;
* desfecho assistencial.

---

# 💰 Ponto de Coleta 14 — Dados Administrativos e Financeiros

## Exemplos de Dados

* autorização;
* faturamento;
* glosas;
* convênios;
* valores faturados;
* recebimentos.

## Potencial Analítico

* sustentabilidade institucional;
* análise financeira;
* perfil econômico;
* margem operacional.

---

# 😊 Ponto de Coleta 15 — Experiência do Paciente

## Exemplos de Dados

* pesquisa de satisfação;
* reclamações;
* elogios;
* manifestações;
* tempo de resposta.

## Potencial Analítico

* experiência do paciente;
* qualidade percebida;
* relacionamento institucional.

---

# 🛡️ Rastreabilidade da Informação

Cada dado institucional poderá possuir:

* origem operacional;
* responsável pelo registro;
* contexto institucional;
* data/hora de geração;
* histórico de alterações;
* vínculo com eventos operacionais;
* vínculo analítico.

Esse mecanismo fortalece:

* auditoria;
* governança;
* confiabilidade institucional;
* análise histórica;
* rastreabilidade operacional.

---

# 📊 Síntese dos Pontos de Coleta

| Ponto de Coleta             | Natureza Predominante   | Potencial de Reutilização |
| --------------------------- | ----------------------- | ------------------------- |
| Entrada e admissão          | Primária                | Muito alta                |
| Triagem                     | Primária / complementar | Alta                      |
| Atendimento assistencial    | Primária / complementar | Muito alta                |
| Observação                  | Primária / derivada     | Alta                      |
| Internação                  | Primária / estruturante | Muito alta                |
| Acompanhamento assistencial | Primária / complementar | Muito alta                |
| Unidade crítica             | Primária / derivada     | Muito alta                |
| Dispositivos e bundles      | Primária / complementar | Muito alta                |
| Procedimentos               | Primária / complementar | Alta                      |
| Qualidade e eventos         | Complementar            | Alta                      |
| Vigilância e CCIH           | Primária / complementar | Alta                      |
| Movimentações internas      | Primária                | Muito alta                |
| Alta e desfecho             | Primária                | Muito alta                |
| Administrativo e financeiro | Primária / complementar | Muito alta                |
| Experiência do paciente     | Complementar            | Média / alta              |

---

# 🚀 Implicações Arquiteturais

A arquitetura da plataforma deve considerar que:

* os dados possuem ciclo evolutivo;
* os registros são temporalmente relevantes;
* múltiplos módulos compartilham informações;
* eventos operacionais geram rastreabilidade;
* dados operacionais alimentam analytics;
* informações podem ser consolidadas progressivamente.

Além disso, a solução deve permitir:

* reutilização de dados;
* redução de redundância;
* evolução incremental da modelagem;
* suporte à análise histórica;
* expansão futura para BI e inteligência analítica.

---

# 🔮 Direcionamentos Evolutivos

Esta arquitetura prepara a plataforma para evolução futura envolvendo:

* analytics institucional;
* business intelligence;
* governança de dados;
* consolidação analítica;
* rastreabilidade avançada;
* inteligência operacional;
* automações institucionais;
* modelos preditivos e IA.

---
