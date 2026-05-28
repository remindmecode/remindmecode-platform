# 📚 Modelagem — Dicionário de Dados

> **Documento:** Dicionário de Dados  
> **Código:** DOC-MOD-003  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Definir de forma padronizada os dados utilizados pela plataforma REMINDMECODE, estabelecendo significado, estrutura, finalidade e regras conceituais para suporte à modelagem, persistência, analytics e rastreabilidade institucional.

---

# 🧠 Contexto

O dicionário de dados atua como referência semântica central da plataforma.

Seu objetivo é garantir:

* entendimento comum entre áreas técnicas e operacionais;
* consistência estrutural;
* reutilização de dados;
* padronização da persistência;
* suporte à camada analítica;
* alinhamento entre domínio e implementação.

O documento não representa implementação física final do banco, mas sim a definição conceitual dos dados da plataforma.

---

# 🧩 Princípios do Dicionário de Dados

## Fonte única de verdade

Cada dado possui definição única dentro da plataforma.

---

## Clareza semântica

Todo campo deve possuir significado explícito e compreensível.

---

## Reutilização estrutural

Dados devem ser reutilizados entre módulos sempre que possível.

---

## Independência tecnológica

O significado do dado é definido independentemente da implementação técnica.

---

## Orientação analítica

A modelagem considera futura utilização para indicadores, auditoria e analytics institucional.

---

# 🧱 Estrutura Padrão dos Campos

Cada definição deve conter:

| Atributo      | Descrição                    |
| ------------- | ---------------------------- |
| Nome          | Nome conceitual do campo     |
| Descrição     | Significado funcional        |
| Tipo          | Tipo lógico do dado          |
| Obrigatório   | Define obrigatoriedade       |
| Origem        | Origem operacional do dado   |
| Classificação | Natureza do dado             |
| Observações   | Regras ou contexto adicional |

---

# 🧠 Classificação Conceitual dos Dados

| Classificação | Descrição                             |
| ------------- | ------------------------------------- |
| Primário      | Dado principal gerado no processo     |
| Complementar  | Informação de apoio/contexto          |
| Derivado      | Calculado a partir de outros dados    |
| Referencial   | Utilizado como vínculo estrutural     |
| Analítico     | Utilizado para indicadores e métricas |

---

# 🏥 Entidade: Paciente

## Finalidade

Representa o indivíduo assistido pela instituição.

| Campo           | Descrição                       | Tipo      | Obrigatório | Origem   | Classificação |
| --------------- | ------------------------------- | --------- | ----------- | -------- | ------------- |
| patient_id      | Identificador único do paciente | UUID      | Sim         | Sistema  | Primário      |
| full_name       | Nome completo do paciente       | Texto     | Sim         | Admissão | Primário      |
| birth_date      | Data de nascimento              | Data      | Sim         | Admissão | Primário      |
| gender          | Sexo biológico                  | Texto     | Não         | Admissão | Complementar  |
| document_number | Documento identificador         | Texto     | Não         | Cadastro | Complementar  |
| created_at      | Data de criação do registro     | Timestamp | Sim         | Sistema  | Referencial   |

---

# 🏥 Entidade: Atendimento

## Finalidade

Representa o primeiro contato operacional do paciente com a instituição.

| Campo           | Descrição                    | Tipo      | Obrigatório | Origem      | Classificação |
| --------------- | ---------------------------- | --------- | ----------- | ----------- | ------------- |
| attendance_id   | Identificador do atendimento | UUID      | Sim         | Sistema     | Primário      |
| patient_id      | Referência ao paciente       | FK        | Sim         | Sistema     | Referencial   |
| attendance_type | Tipo do atendimento          | Texto     | Sim         | Operacional | Complementar  |
| entry_datetime  | Data e hora de entrada       | Timestamp | Sim         | Operacional | Primário      |
| sector_id       | Setor inicial do atendimento | FK        | Não         | Sistema     | Referencial   |
| created_at      | Data de criação do registro  | Timestamp | Sim         | Sistema     | Referencial   |

---

# 🏥 Entidade: Internação

## Finalidade

Representa o período de permanência hospitalar do paciente.

| Campo              | Descrição                    | Tipo      | Obrigatório | Origem       | Classificação |
| ------------------ | ---------------------------- | --------- | ----------- | ------------ | ------------- |
| admission_id       | Identificador da internação  | UUID      | Sim         | Sistema      | Primário      |
| patient_id         | Referência ao paciente       | FK        | Sim         | Sistema      | Referencial   |
| attendance_id      | Atendimento relacionado      | FK        | Não         | Sistema      | Referencial   |
| admission_datetime | Data/hora da internação      | Timestamp | Sim         | Assistencial | Primário      |
| discharge_datetime | Data/hora da alta            | Timestamp | Não         | Assistencial | Primário      |
| initial_sector_id  | Setor inicial                | FK        | Sim         | Sistema      | Referencial   |
| status             | Situação atual da internação | Texto     | Sim         | Sistema      | Complementar  |

---

# 🏥 Entidade: Movimentação

## Finalidade

Representa mudanças de localização assistencial do paciente.

| Campo                 | Descrição                     | Tipo      | Obrigatório | Origem       | Classificação |
| --------------------- | ----------------------------- | --------- | ----------- | ------------ | ------------- |
| movement_id           | Identificador da movimentação | UUID      | Sim         | Sistema      | Primário      |
| admission_id          | Internação relacionada        | FK        | Sim         | Sistema      | Referencial   |
| origin_sector_id      | Setor de origem               | FK        | Não         | Sistema      | Referencial   |
| destination_sector_id | Setor de destino              | FK        | Sim         | Sistema      | Referencial   |
| movement_datetime     | Momento da movimentação       | Timestamp | Sim         | Assistencial | Primário      |
| reason                | Motivo da movimentação        | Texto     | Não         | Assistencial | Complementar  |

---

# 🏥 Entidade: Leito

## Finalidade

Representa recurso físico assistencial utilizado na internação.

| Campo     | Descrição                          | Tipo    | Obrigatório | Origem      | Classificação |
| --------- | ---------------------------------- | ------- | ----------- | ----------- | ------------- |
| bed_id    | Identificador do leito             | UUID    | Sim         | Sistema     | Primário      |
| sector_id | Setor vinculado                    | FK      | Sim         | Sistema     | Referencial   |
| code      | Código operacional do leito        | Texto   | Sim         | Operacional | Complementar  |
| status    | Situação atual                     | Texto   | Sim         | Sistema     | Complementar  |
| active    | Indica disponibilidade operacional | Boolean | Sim         | Sistema     | Complementar  |

---

# 🏥 Entidade: Evento

## Finalidade

Representa ocorrências operacionais, assistenciais ou institucionais.

| Campo          | Descrição               | Tipo      | Obrigatório | Origem      | Classificação |
| -------------- | ----------------------- | --------- | ----------- | ----------- | ------------- |
| event_id       | Identificador do evento | UUID      | Sim         | Sistema     | Primário      |
| patient_id     | Paciente relacionado    | FK        | Não         | Sistema     | Referencial   |
| admission_id   | Internação relacionada  | FK        | Não         | Sistema     | Referencial   |
| event_type     | Tipo do evento          | Texto     | Sim         | Operacional | Complementar  |
| event_datetime | Data/hora do evento     | Timestamp | Sim         | Operacional | Primário      |
| description    | Descrição complementar  | Texto     | Não         | Operacional | Complementar  |

---

# 🏥 Entidade: Dispositivo

## Finalidade

Representa dispositivos assistenciais utilizados no cuidado do paciente.

| Campo       | Descrição                    | Tipo    | Obrigatório | Origem       | Classificação |
| ----------- | ---------------------------- | ------- | ----------- | ------------ | ------------- |
| device_id   | Identificador do dispositivo | UUID    | Sim         | Sistema      | Primário      |
| device_type | Tipo do dispositivo          | Texto   | Sim         | Assistencial | Complementar  |
| description | Descrição operacional        | Texto   | Não         | Assistencial | Complementar  |
| active      | Situação de disponibilidade  | Boolean | Sim         | Sistema      | Complementar  |

---

# 🏥 Entidade: Uso de Dispositivo

## Finalidade

Representa utilização temporal de dispositivos durante internação.

| Campo           | Descrição              | Tipo      | Obrigatório | Origem       | Classificação |
| --------------- | ---------------------- | --------- | ----------- | ------------ | ------------- |
| device_usage_id | Identificador do uso   | UUID      | Sim         | Sistema      | Primário      |
| device_id       | Dispositivo utilizado  | FK        | Sim         | Sistema      | Referencial   |
| admission_id    | Internação relacionada | FK        | Sim         | Sistema      | Referencial   |
| start_datetime  | Início da utilização   | Timestamp | Sim         | Assistencial | Primário      |
| end_datetime    | Final da utilização    | Timestamp | Não         | Assistencial | Primário      |

---

# ⏱️ Dados Temporais

Campos temporais possuem importância estrutural para:

* analytics;
* rastreabilidade;
* auditoria;
* indicadores;
* reconstrução de jornada assistencial.

Padrões utilizados:

| Tipo           | Finalidade          |
| -------------- | ------------------- |
| created_at     | criação do registro |
| updated_at     | atualização         |
| deleted_at     | remoção lógica      |
| event_datetime | momento operacional |
| start_datetime | início de período   |
| end_datetime   | término de período  |

---

# 🔗 Dados Referenciais

Campos FK representam vínculos estruturais entre entidades.

Objetivos:

* garantir integridade;
* evitar duplicidade;
* permitir rastreabilidade;
* sustentar analytics relacionais.

---

# 📊 Dados Derivados

Alguns dados não são persistidos diretamente, sendo calculados pela camada analítica.

## Exemplos

| Dado derivado              | Origem                 |
| -------------------------- | ---------------------- |
| tempo de permanência       | internação             |
| taxa de ocupação           | leitos + movimentações |
| tempo de espera            | atendimento + eventos  |
| utilização de dispositivos | uso_dispositivo        |

---

# 🔄 Evolução do Dicionário

O dicionário poderá evoluir conforme:

* surgimento de novos módulos;
* expansão institucional;
* evolução analítica;
* integração com sistemas externos;
* amadurecimento do domínio.

Toda inclusão de novos dados deve priorizar:

* clareza semântica;
* reutilização;
* rastreabilidade;
* baixo acoplamento;
* consistência estrutural.

---