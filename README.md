# Site-CASIS
# 🎓 Site do Centro Acadêmico CASIS

Bem-vindo ao repositório oficial do site do Centro Acadêmico de Sistemas de Informação (CASIS) da UTFPR!

---

## 📚 1. Visão Geral do Projeto
Este projeto é uma plataforma web desenvolvida para:
- Gerenciamento de eventos 📅
- Envio de denúncias anônimas 🕵️
- Emissão de certificados 📄

Utilizamos **PHP**, **HTML**, **CSS**, **JavaScript** e **MySQL/PostgreSQL**, organizados no padrão **MVC** (Model-View-Controller) para garantir uma estrutura escalável e eficiente.

---

## 🚀 2. Funcionalidades

### 🕵️‍♂️ Denúncias Anônimas
- Formulário simples e seguro para denúncias anônimas.
- Visualização de denúncias para administradores.
- Atualização do status de denúncias (pendente/resolvida).

### 📅 Criação e Gerenciamento de Eventos
- Cadastro e edição de eventos com título, descrição, data, local e organizador.
- Inscrição de usuários nos eventos.
- Geração automática de **certificados em PDF**.

### 🛠️ Área Administrativa
- Dashboard para gerenciar eventos e denúncias.
- Controle de status dos eventos (ativo ou finalizado).
- Emissão e download de certificados.

---

## 🛠️ 3. Estrutura MVC

### 🗄️ Model
- `DenunciaModel`: Gerencia denúncias.
- `EventoModel`: Gerencia eventos.
- `InscricaoModel`: Gerencia inscrições.
- `CertificadoModel`: Gera certificados.

### 🎨 View
- Página inicial
- Página de envio de denúncias
- Listagem de eventos e inscriçõesA
- Área administrativa

### 🎯 Controller
- `DenunciaController`
- `EventoController`
- `CertificadoController`

---

## 🗃️ 4. Estrutura do Banco de Dados

**Tabelas Principais:**
- **Usuários:** `id`, `nome`, `email`, `senha` (hash), `tipo_usuario`
- **Denúncias:** `id`, `descricao`, `data_envio`, `status`
- **Eventos:** `id`, `nome`, `descricao`, `data_inicio`, `data_fim`, `local`, `organizador`, `status`
- **Inscrições:** `id`, `id_evento`, `id_usuario`, `status`
- **Certificados:** `id`, `id_evento`, `id_usuario`, `data_emissao`

**Relacionamentos:**
- Um usuário pode se inscrever em vários eventos.
- Um evento pode gerar vários certificados.
- Denúncias são independentes.

---

## ⚙️ 5. Tecnologias Utilizadas

- **PHP** 🐘 — Backend
- **MySQL/PostgreSQL** 🛢️ — Banco de dados
- **HTML/CSS/JavaScript** 🎨 — Frontend
- **Bootstrap** 🧩 — Design Responsivo
- **AJAX/jQuery** ⚡ — Interações Dinâmicas
- **TCPDF/FPDF** 📄 — Geração de PDFs

---

## 🔄 6. Fluxo de Trabalho

### 📬 Denúncias
1. Usuário preenche e envia o formulário de denúncia.
2. Denúncia salva como "pendente".
3. Administrador visualiza e altera o status conforme resolvido.

### 📅 Eventos
1. Administrador cria e gerencia eventos.
2. Usuário se inscreve nos eventos.
3. Certificados são gerados após finalização do evento.

### 📄 Certificados
- Geração automática contendo:
  - Nome do participante
  - Nome do evento
  - Datas e assinatura digital (opcional)

---

## 🔒 7. Segurança

- **Autenticação:** Login obrigatório para ações importantes.
- **Senhas:** Criptografadas com `bcrypt`.
- **Validação:** Frontend + Backend para máxima proteção contra ataques (SQL Injection, XSS, etc).

---

## 🌐 8. Hospedagem e Deploy

- **Hospedagem:** Plataformas compatíveis com PHP e MySQL (ex: Hostinger, DigitalOcean).
- **Versionamento:** Git + GitHub 🚀
- **Deploy:** Automatizado com FTP/SFTP ou plataformas como Heroku.

---

## 📌 Contribuindo
Sinta-se à vontade para abrir issues, sugerir melhorias ou enviar pull requests! 💬

---

> Feito com ❤️ pelo CASIS
