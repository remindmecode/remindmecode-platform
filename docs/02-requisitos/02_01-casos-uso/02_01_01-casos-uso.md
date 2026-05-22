# 📌 Caso de Uso — Cadastro de Usuário

> **Documento:** Caso de Uso Detalhado
> **Código:** DOC-UC-001
> **Caso de Uso:** UC-ADM-001
> **Versão:** 1.0.0
> **Status:** Em elaboração
> **Última atualização:** 2026-05-22

---

# 🎯 Objetivo

Descrever o fluxo operacional para cadastro de usuários institucionais na plataforma, garantindo controle de acesso, rastreabilidade e governança administrativa.

---

# 🧠 Contexto

O cadastro de usuários é responsável por permitir acesso seguro e controlado à plataforma, vinculando cada usuário a perfis institucionais específicos conforme sua responsabilidade operacional.

---

# 🧾 Identificação

| Campo          | Valor                       |
| -------------- | --------------------------- |
| Caso de Uso    | UC-ADM-001                  |
| Nome           | Cadastrar Usuário           |
| Domínio        | Administração da Plataforma |
| Módulo         | Usuários                    |
| Ator Principal | Administrador               |
| Prioridade     | Alta                        |
| Complexidade   | Baixa                       |
| Status         | Em elaboração               |

---

# 🎭 Atores Envolvidos

| Ator          | Responsabilidade                              |
| ------------- | --------------------------------------------- |
| Administrador | Realizar cadastro e gerenciamento de usuários |
| Plataforma    | Validar regras e persistir informações        |

---

# ✅ Pré-Condições

* administrador autenticado;
* usuário com permissão administrativa;
* perfil institucional previamente definido.

---

# 🚀 Fluxo Principal

| Passo | Ação                                        |
| ----- | ------------------------------------------- |
| 1     | Administrador acessa módulo de usuários     |
| 2     | Plataforma apresenta formulário de cadastro |
| 3     | Administrador informa dados do usuário      |
| 4     | Plataforma valida informações obrigatórias  |
| 5     | Plataforma valida unicidade do email        |
| 6     | Administrador define perfil de acesso       |
| 7     | Plataforma registra usuário                 |
| 8     | Plataforma confirma cadastro realizado      |

---

# ⚠️ Fluxos Alternativos

## FA-01 — Email já cadastrado

| Passo | Ação                                        |
| ----- | ------------------------------------------- |
| 1     | Plataforma identifica email existente       |
| 2     | Plataforma bloqueia cadastro                |
| 3     | Plataforma exibe mensagem de inconsistência |

---

## FA-02 — Dados obrigatórios ausentes

| Passo | Ação                                         |
| ----- | -------------------------------------------- |
| 1     | Plataforma identifica campos inválidos       |
| 2     | Plataforma solicita correção das informações |

---

# ❌ Fluxos de Exceção

## FE-01 — Falha de persistência

| Passo | Ação                                   |
| ----- | -------------------------------------- |
| 1     | Plataforma identifica erro interno     |
| 2     | Cadastro não é concluído               |
| 3     | Evento é registrado em log operacional |

---

# 📌 Pós-Condições

* usuário institucional cadastrado;
* perfil de acesso associado;
* registro persistido;
* evento registrado para auditoria.

---

# 🔐 Regras Relacionadas

| Regra  | Descrição                                       |
| ------ | ----------------------------------------------- |
| RN-001 | Email deve ser único                            |
| RN-004 | Apenas administradores podem cadastrar usuários |
| RN-006 | Perfil define permissões operacionais           |
| RN-008 | Usuários não devem ser removidos fisicamente    |

---

# 📎 Requisitos Relacionados

| Requisito      | Descrição                           |
| -------------- | ----------------------------------- |
| RF-ADM-USR-001 | Cadastro de usuário                 |
| RF-ADM-USR-006 | Controle de acesso                  |
| RNF-SEG-001    | Armazenamento seguro de credenciais |

---

# 🔄 Observações

Este caso de uso representa a visão inicial do fluxo administrativo de usuários e poderá evoluir conforme expansão dos mecanismos de autenticação, governança institucional e integração com diretórios externos.
