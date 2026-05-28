# 🔤 Padrões — Nomenclatura

> **Documento:** Padrões de Nomenclatura  
> **Código:** DOC-PTN-003  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Definir os padrões de nomenclatura adotados no projeto REMINDMECODE, garantindo consistência, clareza, rastreabilidade e alinhamento técnico entre backend, frontend, banco de dados, documentação e artefatos institucionais.

---

# 🧠 Contexto

A padronização de nomenclaturas é essencial para:

* facilitar manutenção;
* reduzir ambiguidades;
* melhorar legibilidade;
* simplificar navegação no código;
* apoiar escalabilidade;
* manter consistência entre módulos;
* alinhar linguagem técnica e domínio institucional.

Os padrões definidos neste documento deverão ser utilizados em toda a plataforma.

---

# 🌐 Idioma do Projeto

## Código-fonte

O código deverá ser escrito em inglês.

Abrange:

* classes;
* métodos;
* variáveis;
* tabelas;
* endpoints;
* DTOs;
* serviços;
* componentes;
* estruturas técnicas.

---

## Documentação

A documentação institucional e arquitetural poderá ser escrita em português.

---

## Domínio Institucional

Termos hospitalares poderão refletir a realidade operacional da instituição, desde que mantenham:

* clareza;
* consistência;
* rastreabilidade conceitual.

---

# 🧩 Convenções do Backend

## Classes

### Padrão

Utilizar **PascalCase**.

### Exemplos

```java
Patient
Admission
HospitalBed
OperationalDashboard
PatientService
AuditEvent
```

---

## Interfaces

### Padrão

Utilizar prefixo descritivo quando necessário.

### Exemplos

```java
PatientRepository
AuthenticationService
DashboardMapper
```

---

## Métodos

### Padrão

Utilizar **camelCase** e iniciar com verbo.

### Exemplos

```java
createPatient()
findAdmissions()
calculateLengthOfStay()
registerOperationalEvent()
generateAnalyticsReport()
```

---

## Variáveis

### Padrão

Utilizar **camelCase** com nomes claros e sem abreviações desnecessárias.

### Exemplos

```java
patientName
admissionDate
hospitalUnit
operationalIndicator
dashboardResponse
```

---

## Constantes

### Padrão

Utilizar **UPPER_SNAKE_CASE**.

### Exemplos

```java
DEFAULT_PAGE_SIZE
MAX_LOGIN_ATTEMPTS
TOKEN_EXPIRATION_TIME
```

---

## Pacotes

### Padrão

Utilizar nomes em minúsculo.

### Exemplos

```text
controller
service
repository
security
validation
analytics
audit
```

---

# 🌐 Convenções do Frontend

## Componentes React

### Padrão

Utilizar **PascalCase**.

### Exemplos

```text
PatientCard
DashboardChart
OperationalTable
AuditTimeline
```

---

## Hooks

### Padrão

Utilizar prefixo `use`.

### Exemplos

```text
useAuthentication
useDashboardData
useOperationalIndicators
```

---

## Arquivos Frontend

### Padrão

Utilizar **kebab-case**.

### Exemplos

```text
patient-service.ts
dashboard-chart.tsx
operational-table.tsx
authentication-hook.ts
```

---

# 🗄️ Convenções do Banco de Dados

## Tabelas

### Padrão

Utilizar **snake_case** no singular.

### Exemplos

```sql
patient
admission
hospital_bed
audit_event
operational_indicator
```

---

## Colunas

### Padrão

Utilizar **snake_case**.

### Exemplos

```sql
patient_id
admission_date
created_at
updated_at
hospital_unit
```

---

## Chaves Primárias

### Padrão

Utilizar `id`.

### Exemplo

```sql
id
```

---

## Chaves Estrangeiras

### Padrão

Utilizar:

```sql
<entity>_id
```

### Exemplos

```sql
patient_id
admission_id
bed_id
```

---

## Timestamps

### Padrão

Utilizar nomenclatura padronizada.

### Exemplos

```sql
created_at
updated_at
deleted_at
processed_at
```

---

# 🔗 Convenções de API

## Endpoints

### Padrão

Utilizar:

* minúsculas;
* kebab-case;
* substantivos claros;
* sem abreviações desnecessárias.

### Exemplos

```http
/api/patients
/api/admissions
/api/hospital-beds
/api/operational-indicators
/api/audit-events
```

---

## Recursos REST

### Direcionamento

Os endpoints deverão representar recursos institucionais.

### Exemplos

```http
GET    /patients
POST   /patients
PUT    /patients/{id}
DELETE /patients/{id}
```

---

# 📄 Convenções de Arquivos

## Arquivos Markdown

### Padrão

Utilizar **kebab-case**.

### Exemplos

```text
architecture-overview.md
data-flow.md
operational-dashboard.md
activity-diagram.md
```

---

## Diagramas UML

### Padrão

Utilizar:

```text
<codigo>-<descricao>.png
```

### Exemplos

```text
dat-adm-001-user-registration.png
uc-opr-001-operational-data.png
erd-hospital-model.png
```

---

# 📚 Convenções de Documentação

## Código documental

### Estrutura

```text
DOC-<DOMINIO>-<NUMERO>
```

### Exemplos

```text
DOC-ARC-001
DOC-GST-003
DOC-PTN-002
DOC-UCM-001
```

---

## Prefixos institucionais

| Prefixo | Significado            |
| ------- | ---------------------- |
| ARC     | Arquitetura            |
| GST     | Gestão                 |
| PTN     | Padrões                |
| UCM     | Casos de Uso           |
| UAT     | Diagramas de Atividade |
| UML     | Modelagem UML          |

---

# 🧠 Convenções de Branches

## Feature

```text
feature/<descricao>
```

### Exemplo

```text
feature/architecture-documentation
```

---

## Bugfix

```text
bugfix/<descricao>
```

---

## Hotfix

```text
hotfix/<descricao>
```

---

## Chore

```text
chore/<descricao>
```

---

# 🔄 Direcionamentos Gerais

Os nomes utilizados no projeto devem priorizar:

* clareza;
* previsibilidade;
* baixo acoplamento conceitual;
* aderência ao domínio hospitalar;
* facilidade de manutenção;
* padronização técnica.

Evitar:

* abreviações ambíguas;
* siglas sem contexto;
* nomes genéricos;
* termos inconsistentes;
* mistura de idiomas no mesmo contexto técnico.

---

# 🔮 Evolução dos Padrões

Os padrões de nomenclatura poderão evoluir conforme:

* crescimento da plataforma;
* expansão dos módulos;
* amadurecimento arquitetural;
* evolução das integrações;
* refinamento do domínio institucional.

Mudanças de nomenclatura devem priorizar:

* compatibilidade;
* rastreabilidade;
* consistência global;
* impacto controlado na arquitetura.

---
