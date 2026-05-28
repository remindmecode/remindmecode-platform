# 🏗️ Padrões — Estrutura do Projeto

> **Documento:** Estrutura do Projeto  
> **Código:** DOC-PTN-002  
> **Versão:** 1.0.0  
> **Status:** Em elaboração  
> **Última atualização:** 2026-05-27  

---

# 🎯 Objetivo

Definir a organização estrutural do projeto REMINDMECODE, estabelecendo padrões de organização, modularização e separação de responsabilidades para evolução sustentável da plataforma.

---

# 🧠 Contexto

A estrutura do projeto foi concebida para:

* facilitar manutenção;
* reduzir acoplamento;
* permitir evolução incremental;
* apoiar modularização institucional;
* melhorar rastreabilidade técnica;
* simplificar navegação no código e documentação.

A organização estrutural acompanha os princípios arquiteturais definidos para a plataforma.

---

# 🧩 Organização Geral da Plataforma

O projeto é organizado em:

* backend;
* frontend;
* documentação;
* database;
* artefatos auxiliares.

A estrutura busca separar claramente:

* regras de negócio;
* entrada de dados;
* persistência;
* visualização;
* integrações;
* documentação técnica.

---

# 🖥️ Estrutura do Backend

## Organização Base

```text
src/
 └── main/
     └── java/
         └── com/remindmecode/
             ├── controller/
             ├── service/
             ├── repository/
             ├── entity/
             ├── dto/
             ├── mapper/
             ├── config/
             ├── security/
             ├── exception/
             ├── validation/
             └── util/
```

---

# 🧱 Responsabilidades das Camadas

## controller

Responsável por:

* exposição de endpoints;
* entrada da aplicação;
* recebimento de requisições;
* validações iniciais;
* controle HTTP.

---

## service

Responsável por:

* regras de negócio;
* orquestração operacional;
* processamento institucional;
* validações funcionais.

---

## repository

Responsável por:

* acesso ao banco de dados;
* persistência;
* consultas;
* abstração da camada de dados.

---

## entity

Responsável por:

* representação das entidades persistidas;
* mapeamento relacional;
* estrutura do domínio persistente.

---

## dto

Responsável por:

* transporte de dados;
* contratos de entrada e saída;
* desacoplamento entre API e persistência.

---

## mapper

Responsável por:

* conversão entre entidades e DTOs;
* transformação de estruturas de dados.

---

## config

Responsável por:

* configurações da aplicação;
* beans;
* infraestrutura técnica;
* inicialização de componentes.

---

## security

Responsável por:

* autenticação;
* autorização;
* controle de acesso;
* segurança institucional.

---

## exception

Responsável por:

* tratamento centralizado de exceções;
* padronização de erros.

---

## validation

Responsável por:

* validações reutilizáveis;
* regras estruturais;
* consistência de entrada.

---

## util

Responsável por:

* funções auxiliares;
* componentes compartilhados;
* abstrações reutilizáveis.

---

# 🌐 Estrutura do Frontend

## Organização Base

```text
src/
 ├── components/
 ├── pages/
 ├── layouts/
 ├── services/
 ├── hooks/
 ├── context/
 ├── routes/
 ├── utils/
 ├── styles/
 └── assets/
```

---

# 🧩 Responsabilidades do Frontend

| Diretório  | Responsabilidade          |
| ---------- | ------------------------- |
| components | Componentes reutilizáveis |
| pages      | Telas da aplicação        |
| layouts    | Estruturas visuais        |
| services   | Comunicação com APIs      |
| hooks      | Hooks customizados        |
| context    | Gerenciamento de contexto |
| routes     | Roteamento                |
| utils      | Utilidades compartilhadas |
| styles     | Estilos globais           |
| assets     | Recursos estáticos        |

---

# 🧠 Evolução para Organização por Domínio

A estrutura poderá evoluir progressivamente para abordagem orientada a domínio.

Exemplo:

```text
patient/
admission/
bed/
dashboard/
analytics/
audit/
```

Cada domínio poderá possuir:

* controllers;
* services;
* repositories;
* DTOs;
* validações;
* regras específicas.

---

# 📦 Modularização Institucional

A plataforma é organizada em módulos institucionais independentes.

## Módulos iniciais

* administração da plataforma;
* operação institucional;
* gestão operacional;
* analytics institucional;
* auditoria e governança.

---

# 📚 Organização da Documentação

A documentação do projeto é organizada por áreas de responsabilidade.

## Estrutura Base

```text
docs/
 ├── 01-produto/
 ├── 02-requisitos/
 ├── 03-arquitetura/
 ├── 04-gestao/
 ├── 05-prototipacao/
 ├── 06-modelagem/
 ├── 07-uml/
 ├── 08-padroes/
 ├── 09-qualidade/
 ├── 10-seguranca/
 ├── 11-versionamento/
 ├── 12-deploy/
 ├── 13-roadmap/
 ├── 14-observabilidade/
 └── 15-discovery/
```

---

# 🔄 Evolução Estrutural

A estrutura do projeto poderá evoluir conforme:

* crescimento da plataforma;
* aumento de módulos;
* necessidade de escalabilidade;
* amadurecimento arquitetural;
* evolução dos domínios institucionais.

Mudanças estruturais devem priorizar:

* baixo acoplamento;
* alta coesão;
* rastreabilidade;
* modularidade;
* simplicidade operacional.

---