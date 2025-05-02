# Site-CASIS
# 🎓 Site do Centro Acadêmico CASIS

Bem-vindo ao repositório oficial do site do Centro Acadêmico de Sistemas de Informação (CASIS) da UTFPR!

---

## 📚 1. Visão Geral do Projeto
Este projeto é uma plataforma web desenvolvida para:
- Gerenciamento de eventos 📅
- Envio de denúncias anônimas 🕵️
- Emissão de certificados 📄
- Controle de presença e check-in com QR Code ✅
- Geração de crachás com fotos 🪪

Utilizamos **PHP**, **HTML**, **CSS**, **JavaScript** e **MySQL/PostgreSQL**, organizados no padrão **MVC** (Model-View-Controller) para garantir uma estrutura escalável e eficiente.

### 🚀 Escalabilidade
- Arquitetura pronta para adição de novas funcionalidades (ex: votações online, enquetes, fóruns, sistema de chamada para aulas).
- Banco de dados estruturado com integridade e normalização para suportar grande volume de usuários e eventos.
- Possibilidade de migração para servidores mais robustos e uso de cache (Redis) e balanceamento de carga.

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

### ✅ Controle de Presença e Check-in
- Sistema de **check-in com leitura de QR Code**.
- Controle de presença para oficinas, palestras e eventos.
- Relatórios de participantes presentes e ausentes.

### 🪪 Geração de Crachás
- Cadastro de alunos com upload de fotos.
- Geração automática de crachás personalizados em PDF.
- Crachás podem incluir foto, nome, curso e QR Code.

### 🛠️ Área Administrativa
- Dashboard para gerenciar eventos, denúncias e presenças.
- Controle de status dos eventos (ativo ou finalizado).
- Emissão e download de certificados e crachás.

---

## 🛠️ 3. Estrutura MVC

### 🗄️ Model
- `DenunciaModel`: Gerencia denúncias.
- `EventoModel`: Gerencia eventos.
- `InscricaoModel`: Gerencia inscrições.
- `CertificadoModel`: Gera certificados.
- `PresencaModel`: Registra presenças.
- `CrachaModel`: Gera crachás.

### 🎨 View
- Página inicial
- Página de envio de denúncias
- Listagem de eventos e inscrições
- Página de check-in (leitor de QR Code)
- Área administrativa

### 🎯 Controller
- `DenunciaController`
- `EventoController`
- `CertificadoController`
- `PresencaController`
- `CrachaController`

---

## 🗃️ 4. Estrutura do Banco de Dados

**Tabelas Principais:**
- **Usuários:** `id`, `nome`, `email`, `senha` (hash), `tipo_usuario`, `foto`
- **Denúncias:** `id`, `descricao`, `data_envio`, `status`
- **Eventos:** `id`, `nome`, `descricao`, `data_inicio`, `data_fim`, `local`, `organizador`, `status`
- **Inscrições:** `id`, `id_evento`, `id_usuario`, `status`
- **Certificados:** `id`, `id_evento`, `id_usuario`, `data_emissao`
- **Presenças:** `id`, `id_evento`, `id_usuario`, `data_checkin`
- **Crachás:** `id`, `id_usuario`, `arquivo_pdf`

**Tabelas adicionais para escalabilidade:**
- **Votações:** `id`, `titulo`, `descricao`, `data_inicio`, `data_fim`, `status`
- **Opções_Votacao:** `id`, `id_votacao`, `opcao`
- **Votos:** `id`, `id_votacao`, `id_usuario`, `id_opcao`
- **Enquetes:** `id`, `pergunta`, `data_inicio`, `data_fim`, `status`
- **Respostas_Enquete:** `id`, `id_enquete`, `id_usuario`, `resposta`
- **Foruns:** `id`, `titulo`, `descricao`, `data_criacao`, `status`
- **Topicos:** `id`, `id_forum`, `titulo`, `descricao`, `id_usuario`, `data_criacao`
- **Respostas_Topico:** `id`, `id_topico`, `id_usuario`, `resposta`, `data_resposta`

**Relacionamentos:**
- Um usuário pode se inscrever e fazer check-in em vários eventos.
- Um evento pode gerar vários certificados e presenças.
- Denúncias são independentes.
- Cada usuário pode ter um crachá gerado.
- Um usuário pode votar e responder enquetes.
- Fóruns podem conter tópicos e respostas.

---

## ⚙️ 5. Tecnologias Utilizadas

- **PHP** 🐘 — Backend
- **MySQL/PostgreSQL** 🛢️ — Banco de dados
- **HTML/CSS/JavaScript** 🎨 — Frontend
- **Bootstrap** 🧩 — Design Responsivo
- **AJAX/jQuery** ⚡ — Interações Dinâmicas
- **TCPDF/FPDF** 📄 — Geração de PDFs
- **Instascan.js** 📷 — Leitura de QR Codes no navegador

---

## 🔄 6. Fluxo de Trabalho

### 📬 Denúncias
1. Usuário preenche e envia o formulário de denúncia.
2. Denúncia salva como "pendente".
3. Administrador visualiza e altera o status conforme resolvido.

### 📅 Eventos
1. Administrador cria e gerencia eventos.
2. Usuário se inscreve nos eventos.
3. Usuário faz **check-in** presencial usando QR Code.
4. Certificados são gerados após finalização do evento.

### ✅ Presença
- Check-in via QR Code registra a presença automaticamente.
- Presenças podem ser visualizadas e exportadas na área admin.

### 🪪 Crachás
- Admin cadastra usuários com fotos.
- Sistema gera crachás com foto e QR Code.
- Crachás podem ser impressos ou baixados em PDF.

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
- **QR Codes:** Gerados de forma única e criptografada para cada usuário.

---

## 🌐 8. Hospedagem e Deploy

- **Hospedagem:** Plataformas compatíveis com PHP e MySQL (ex: Hostinger, DigitalOcean).
- **Versionamento:** Git + GitHub 🚀
- **Deploy:** Automatizado com FTP/SFTP ou plataformas como Heroku.

---

## 📌 Contribuindo
Sinta-se à vontade para abrir issues, sugerir melhorias ou enviar pull requests! 💬

---

> Feito com ❤️ pelo CASIS — Centro Acadêmico de Sistemas de Informação da UTFPR Francisco Beltrão.
