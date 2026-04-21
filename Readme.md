# 📊 Portefolio – Painel Pessoal (Flask)

## 📌 Descrição
Aplicação web pessoal desenvolvida em **Flask**, que funciona como um painel central para gestão de várias áreas do dia-a-dia:

- Mensagens internas  
- Consumo de carro (abastecimentos)  
- Dívidas e pagamentos  
- Gestão de trabalho (turnos, férias, folgas)  
- Administração e monitorização  

Projeto orientado para uso real, com autenticação, controlo de sessão e funcionalidades administrativas.

---

## ⚙️ Tecnologias Utilizadas

- **Python 3**
- **Flask**
- **SQLite**
- **Jinja2**
- **Werkzeug (hash de passwords)**
- **Flask-WTF (CSRF Protection)**
- **ProxyFix (suporte reverse proxy)**
- **Requests (integração com APIs externas)**
- HTML / CSS / JS

---

## 🔐 Funcionalidades Principais

### 👤 Autenticação
- Login e registo de utilizadores  
- Sessões com timeout automático  
- Hash seguro de passwords  
- Logout automático após alteração de password  

---

### 🏠 Painel Principal
- Página central após login  
- Acesso rápido aos módulos:
  - Mensagens  
  - Consumo de carro  
  - Dívidas  
  - Trabalho  
- Integração de **meteorologia em tempo real (Open-Meteo API)**  
- Interface otimizada para desktop e mobile  

---

### 🌦️ Meteorologia (Nova funcionalidade)
- Temperatura atual  
- Estado do tempo (descrição + ícone)  
- Velocidade do vento  
- Localização fixa (Oliveira do Hospital)  
- Atualização automática sem refresh da página (AJAX)  

---

### 💬 Mensagens Internas
- Inbox de mensagens  
- Leitura de mensagens  
- Envio de novas mensagens  
- Eliminação de mensagens  
- Contador de mensagens não lidas  

---

### 🚗 Consumo de Carro
- Registo de abastecimentos  
- Gestão de locais de abastecimento  
- Dashboard com:
  - Total gasto  
  - Litros consumidos  
  - Km percorridos  
  - Média de consumo (L/100km)  
  - Custo por km  

---

### 💰 Dívidas e Pagamentos
- Registo de dívidas  
- Registo de pagamentos  
- Dashboard com:
  - Total em dívida  
  - Total pago  
  - Valor restante  
- Histórico recente  

---

### 🧑‍💼 Gestão de Trabalho
- Registo de dias de trabalho  
- Gestão de turnos  
- Férias  
- Folgas  
- Calendário e histórico  

---

### 🛠️ Administração
- Gestão de utilizadores  
- Criação, edição e remoção de utilizadores  
- Restrições:
  - Admins não podem ser apagados  
  - Admins não podem ser rebaixados  
- Interface administrativa dedicada  

---

### 📊 Monitorização e Diagnóstico
- Página de diagnóstico do sistema com:
  - Estado da aplicação  
  - Estado da base de dados  
  - Informações de rede (IP real, proxy, headers)  
  - Ambiente do servidor (Python, sistema, diretórios)  
- Visualização de estatísticas:
  - Utilizadores  
  - Logins  
  - Bots detetados  
- Informação de tamanho de ficheiros (BD e logs)  

---

### 🔐 Segurança
- Registo de logins (sucesso e falha)  
- Deteção de bots  
- Headers de segurança:
  - HSTS  
  - X-Frame-Options  
  - X-Content-Type-Options  
- Proteção CSRF  
- Suporte a proxy (Cloudflare / reverse proxy)  

---

### 💾 Backups e Logs
- Criação de backups:
  - Projeto  
  - Base de dados  
  - Configuração do servidor (Caddy)  
- Listagem de backups locais e remotos  
- Download e remoção de backups  
- Visualização de logs do sistema  
- Integração com logs do servidor  

---

## 🗄️ Base de Dados

Base de dados SQLite (`portefolio.db`) com as principais tabelas:

- `utilizadores`
- `mensagens`
- `abastecimentos`
- `locais_abastecimento`
- `dividas`
- `pagamentos`
- `trabalho`
- `logins`
- `bots_detectados`

---

## 📁 Estrutura do Projeto

## 📁 Estrutura do Projeto
/PORTFOLIO │ ├── app.py ├── utils.py ├── admin.py ├── mensagens.py ├── carro.py ├── despesas.py ├── trabalho.py │ ├── templates/ │   ├── admin/ │   ├── mensagens/ │   ├── carro/ │   ├── despesas/ │   ├── trabalho/ │   └── ... │ ├── static/ │   ├── css/ │   ├── js/ │   └── imagens/ │ ├── portefolio.db └── README.md
---

## ⚠️ Notas Importantes

- O projeto utiliza caminhos locais (ex: backups e logs) que devem ser ajustados para outros ambientes  
- A `SECRET_KEY` deve ser definida via variável de ambiente em produção  
- Sessões configuradas com timeout automático (ajustável)  
- Algumas funcionalidades dependem de APIs externas (ex: meteorologia)  

---

## 🚀 Execução do Projeto

1. Instalar dependências:
```bash
pip install flask flask-wtf requests