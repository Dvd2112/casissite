# Site-CASIS
🎓 **Site do Centro Acadêmico CASIS**  
Bem-vindo ao repositório oficial do site do Centro Acadêmico de Sistemas de Informação (CASIS) da UTFPR!

## 📚 1. Visão Geral do Projeto
Este projeto é uma plataforma web desenvolvida para:

- Gerenciamento de eventos 📅
- Envio de denúncias anônimas 🕵️
- Emissão de certificados 📄
- Controle de presença e check-in com QR Code ✅
- Geração de crachás com fotos 🪪
- Gerenciamento de usuários com permissões e escalabilidade 🚀

Utilizamos **PHP, HTML, CSS, JavaScript e MySQL/PostgreSQL**, organizados no padrão **MVC (Model-View-Controller)** para garantir uma estrutura escalável e eficiente.

🔄 **Totalmente escalável**: Projetado para permitir futuras funcionalidades como:

- Gestão de comissões e cargos do CASIS.
- Histórico completo de participação dos usuários.
- Emissão de relatórios personalizados para todas as áreas.
- Controle granular com sistema de permissões por ação.
- Exportação de dados em formatos CSV/PDF.

## 🚀 2. Funcionalidades

### 🕵️‍♂️ Denúncias Anônimas
- Formulário simples e seguro.
- Visualização e gerenciamento por administradores.
- Alteração de status (pendente/resolvida).

### 📅 Criação e Gerenciamento de Eventos
- Cadastro e edição de eventos com dados completos.
- Inscrição de usuários.
- Geração automática de certificados em PDF.
- Relatórios e exportação.

### ✅ Controle de Presença e Check-in
- Leitura de QR Code.
- Relatórios de presença (com filtro por evento e status).
- Exportação para planilhas.

### 🪪 Geração de Crachás
- Cadastro com upload de fotos.
- Geração automática de crachás em PDF com QR Code.

### 🛠️ Área Administrativa
- Dashboard geral.
- Gestão completa de eventos, denúncias, presenças e usuários.
- Controle por permissões configuráveis.
- Emissão e download de certificados e crachás.

### 👥 Gerenciamento de Usuários e Permissões
- Criação de usuários com permissões específicas.
- Controle granular por ação:
  - Ex: Permissão para "Criar Evento" e outra para "Emitir Relatório de Evento".
- Área para usuário editar apenas seus dados pessoais (nome, senha, foto).

## 🛠️ 3. Estrutura MVC

### 🗄️ Model
- DenunciaModel
- EventoModel
- InscricaoModel
- CertificadoModel
- PresencaModel
- CrachaModel
- UsuarioModel
- PermissaoModel
- UsuarioPermissaoModel

### 🎨 View
- Página inicial
- Formulário de denúncias
- Listagem e inscrição em eventos
- Página de check-in (QR Code)
- Área administrativa com gestão de dados
- Tela do usuário para editar seus dados básicos

### 🎯 Controller
- DenunciaController
- EventoController
- CertificadoController
- PresencaController
- CrachaController
- UsuarioController
- PermissaoController

## 🗃️ 4. Estrutura Completa do Banco de Dados

### 📊 Tabelas Principais

| Tabela              | Descrição                                 |
| ------------------- | ----------------------------------------- |
| usuarios            | Dados dos usuários do sistema             |
| denuncias           | Denúncias anônimas enviadas               |
| eventos             | Eventos cadastrados pelo CASIS            |
| inscricoes          | Inscrições de usuários em eventos         |
| certificados        | Certificados emitidos para participantes  |
| presencas           | Registros de check-in dos eventos         |
| crachas             | Arquivos PDF dos crachás gerados          |
| permissoes          | Lista de todas permissões possíveis       |
| usuario_permissao   | Relacionamento entre usuários e permissões|

### 🗂️ Campos das Principais Tabelas

#### 🧑‍💻 usuarios
- id
- nome
- email
- senha
- tipo_usuario
- foto
- created_at
- updated_at

#### 📝 denuncias
- id
- descricao
- data_envio
- status
- created_at
- updated_at

#### 📅 eventos
- id
- nome
- descricao
- data_inicio
- data_fim
- local
- organizador
- status
- created_at
- updated_at

#### 🎫 inscricoes
- id
- id_evento
- id_usuario
- status
- created_at
- updated_at

#### 📄 certificados
- id
- id_evento
- id_usuario
- data_emissao
- created_at
- updated_at

#### ✅ presencas
- id
- id_evento
- id_usuario
- data_checkin
- created_at
- updated_at

#### 🪪 crachas
- id
- id_usuario
- arquivo_pdf
- created_at
- updated_at

#### 🛡️ permissoes
- id
- nome
- tipo (Ex: 'ação' ou 'relatório')
- descricao
- created_at
- updated_at

#### 🔗 usuario_permissao
- id
- id_usuario
- id_permissao
- valor (booleano: 1 ou 0)
- created_at
- updated_at

## ⚙️ 5. Tecnologias Utilizadas
- **PHP** 🐘 — Backend
- **MySQL/PostgreSQL** 🛢️ — Banco de dados
- **HTML/CSS/JavaScript** 🎨 — Frontend
- **Bootstrap** 🧩 — Design Responsivo
- **AJAX/jQuery** ⚡ — Interações Dinâmicas
- **TCPDF/FPDF** 📄 — Geração de PDFs
- **Instascan.js** 📷 — Leitura de QR Codes no navegador

## 🔄 6. Fluxo de Trabalho

### 📬 Denúncias
- Usuário envia denúncia anônima.
- Admin altera status (pendente/resolvida).

### 📅 Eventos
- Admin cria evento.
- Usuário se inscreve.
- Usuário faz check-in com QR Code.
- Certificados gerados automaticamente.

### ✅ Presença
- Check-in registra presença.
- Relatórios exportáveis.

### 🪪 Crachás
- Cadastro com foto.
- Geração de crachá com QR Code.

### 📄 Certificados
- Geração automática com nome, evento, datas e assinatura.

### 🔐 Usuários e Permissões
- Admin cria usuários com permissões específicas.
- Usuário comum pode editar apenas seus dados pessoais.
- Sistema escalável para controlar cada ação do sistema via permissões.

## 🔒 7. Segurança
- **Autenticação**: Login seguro.
- **Senhas**: Criptografadas com bcrypt.
- **Validações**: Proteção contra SQL Injection e XSS.
- **QR Codes**: Únicos e criptografados.

## 🌐 8. Escalabilidade e Futuro
Estrutura preparada para crescer:

- Adicionar módulos como votações, atas, biblioteca de arquivos 📚
- Gerar relatórios avançados em PDF e CSV 📊
- Sistema multiusuário com controle de cargos e permissões granular 🛡️
- Histórico completo de participação dos membros
- Possibilidade de integração com sistemas da UTFPR

## 📌 Contribuindo
Sinta-se à vontade para abrir issues, sugerir melhorias ou enviar pull requests! 💬

Feito com ❤️ pelo **CASIS — Centro Acadêmico de Sistemas de Informação da UTFPR Francisco Beltrão.**
