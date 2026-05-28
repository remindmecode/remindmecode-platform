# 🔗 Modelagem — Relacionamentos do Modelo de Dados

> **Documento:** Relacionamentos do Modelo de Dados  
> **Código:** DOC-MOD-002  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Definir como as entidades do REMINDMECODE se relacionam estruturalmente, estabelecendo vínculos de integridade, rastreabilidade e suporte à trajetória institucional do paciente.

---

# 🧠 Contexto

Os relacionamentos representam a forma como os dados institucionais se conectam ao longo da operação hospitalar.

A modelagem dos relacionamentos permite:

* reconstrução da trajetória do paciente;
* integridade estrutural dos dados;
* suporte à camada analítica;
* rastreabilidade operacional;
* consolidação institucional da informação.

Os relacionamentos são orientados principalmente:

* à jornada assistencial;
* aos eventos institucionais;
* à temporalidade dos registros;
* à reutilização da informação.

---

# 🧩 Princípios de Modelagem Relacional

# Integridade referencial

Os vínculos entre entidades devem preservar consistência estrutural e impedir registros órfãos quando aplicável.

---

# Modelagem orientada à trajetória

Os relacionamentos refletem eventos e transições ao longo da jornada institucional do paciente.

---

# Reutilização de informação

Os relacionamentos devem evitar duplicação desnecessária de dados.

---

# Baixo acoplamento

As entidades devem manter dependências controladas, favorecendo evolução modular.

---

# Orientação temporal

Grande parte dos relacionamentos possui dependência temporal explícita.

---

# Rastreabilidade institucional

O modelo deve permitir identificar:

* origem do evento;
* contexto operacional;
* evolução histórica;
* vínculos institucionais.

---

# 🧱 Tipos de Relacionamento

# 1:1 — Um para Um

Utilizado quando uma entidade complementa diretamente outra.

## Exemplos

* usuario ↔ perfil_usuario
* paciente ↔ identificacao_paciente

---

# 1:N — Um para Muitos

Relacionamento predominante na plataforma.

## Exemplos

* paciente → atendimentos
* internacao → movimentacoes
* setor → leitos
* atendimento → eventos

---

# N:N — Muitos para Muitos

Implementado através de entidades associativas.

## Exemplos

* paciente ↔ dispositivo
* internacao ↔ evento
* usuario ↔ permissao

---

# 🏥 Relacionamentos Centrais do Domínio

# Paciente

Entidade central da trajetória institucional.

## Relacionamentos

| Relacionamento             | Tipo |
| -------------------------- | ---- |
| paciente → atendimento     | 1:N  |
| paciente → internacao      | 1:N  |
| paciente → evento          | 1:N  |
| paciente → uso_dispositivo | 1:N  |
| paciente → manifestacao    | 1:N  |

---

# Atendimento

Representa contato assistencial inicial ou intermediário.

## Relacionamentos

| Relacionamento                    | Tipo       |
| --------------------------------- | ---------- |
| atendimento → paciente            | N:1        |
| atendimento → evento              | 1:N        |
| atendimento → classificacao_risco | 1:N        |
| atendimento → internacao          | 1:1 ou 1:N |

---

# Internação

Representa permanência institucional do paciente.

## Relacionamentos

| Relacionamento               | Tipo |
| ---------------------------- | ---- |
| internacao → paciente        | N:1  |
| internacao → setor           | N:1  |
| internacao → movimentacao    | 1:N  |
| internacao → uso_dispositivo | 1:N  |
| internacao → evento          | 1:N  |
| internacao → observacao      | 1:N  |

---

# Movimentação

Representa transições internas da internação.

## Relacionamentos

| Relacionamento               | Tipo |
| ---------------------------- | ---- |
| movimentacao → internacao    | N:1  |
| movimentacao → setor_origem  | N:1  |
| movimentacao → setor_destino | N:1  |
| movimentacao → leito_origem  | N:1  |
| movimentacao → leito_destino | N:1  |

---

# Setor

Representa unidade organizacional institucional.

## Relacionamentos

| Relacionamento       | Tipo |
| -------------------- | ---- |
| setor → leito        | 1:N  |
| setor → internacao   | 1:N  |
| setor → evento       | 1:N  |
| setor → movimentacao | 1:N  |

---

# Leito

Representa unidade física assistencial.

## Relacionamentos

| Relacionamento       | Tipo |
| -------------------- | ---- |
| leito → setor        | N:1  |
| leito → movimentacao | 1:N  |

---

# Uso de Dispositivo

Representa utilização temporal de dispositivos assistenciais.

## Relacionamentos

| Relacionamento                | Tipo |
| ----------------------------- | ---- |
| uso_dispositivo → paciente    | N:1  |
| uso_dispositivo → internacao  | N:1  |
| uso_dispositivo → dispositivo | N:1  |

---

# Evento

Representa ocorrências operacionais, assistenciais ou de segurança.

## Relacionamentos

| Relacionamento                | Tipo |
| ----------------------------- | ---- |
| evento → paciente             | N:1  |
| evento → internacao           | N:1  |
| evento → setor                | N:1  |
| evento → classificacao_evento | N:1  |

---

# Indicadores

Entidades analíticas possuem dependência predominantemente lógica.

## Características

* derivadas de múltiplas entidades;
* dependência baseada em consultas;
* baixo acoplamento físico;
* orientação analítica.

---

# ⏱️ Relacionamentos Temporais

Diversas entidades possuem dependência temporal explícita.

## Principais entidades temporais

| Entidade        | Elemento temporal |
| --------------- | ----------------- |
| atendimento     | data/hora         |
| internacao      | início/fim        |
| movimentacao    | timestamp         |
| uso_dispositivo | início/fim        |
| evento          | data/hora         |
| observacao      | permanência       |

---

# 🧠 Relacionamentos Derivados

Alguns vínculos são analíticos e não físicos.

## Exemplos

| Informação derivada   | Origem                    |
| --------------------- | ------------------------- |
| tempo de permanência  | internacao + movimentacao |
| ocupação de leito     | leito + movimentacao      |
| tempo de espera       | atendimento + evento      |
| taxa de utilização    | internacao + setor        |
| permanência por setor | movimentacao              |

Esses relacionamentos são resolvidos na camada analítica.

---

# ⚠️ Regras Estruturais Importantes

# Integridade de contexto

Eventos relevantes devem possuir:

* referência temporal;
* setor relacionado;
* origem operacional.

---

# Preservação histórica

Movimentações não devem sobrescrever histórico anterior.

---

# Evitar duplicação

Informações reutilizáveis devem ser centralizadas.

---

# Preservação da trajetória

O modelo deve permitir reconstrução cronológica da jornada do paciente.

---

# 🔄 Evolução dos Relacionamentos

A modelagem poderá evoluir conforme:

* amadurecimento institucional;
* expansão de módulos;
* aumento da granularidade operacional;
* evolução analítica;
* necessidade de integrações externas.

Mudanças devem priorizar:

* baixo acoplamento;
* integridade;
* rastreabilidade;
* reutilização;
* escalabilidade.

---

# 🚀 Resultado Esperado

A modelagem consistente dos relacionamentos permite que o REMINDMECODE evolua com:

* integridade estrutural;
* rastreabilidade institucional;
* suporte analítico;
* consistência operacional;
* reutilização de dados;
* capacidade de crescimento sustentável.

---
