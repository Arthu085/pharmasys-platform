# PharmaSys Platform

## 📋 Sobre o Projeto

O **PharmaSys** é uma plataforma de gestão farmacêutica desenvolvida para facilitar o controle de estoque, dispensação de medicamentos, entrada e saída de itens, gestão de lotes e localização de estoque em ambientes hospitalares e farmacêuticos.

O sistema oferece:

- 🏥 **Gestão de Empresas**: Controle multi-empresa com hierarquia organizacional
- 💊 **Controle de Estoque**: Gerenciamento completo de itens farmacêuticos
- 📦 **Gestão de Lotes**: Controle de validade e rastreabilidade
- 📝 **Dispensação de Medicamentos**: Registro e controle de dispensações
- 🔄 **Transferências entre Estoques**: Movimentação entre locais de armazenamento
- 👥 **Gestão de Pacientes e Prescritores**: Cadastro e controle completo
- 📊 **Relatórios e Dashboards**: Visualização de métricas e indicadores
- 🔐 **Controle de Acesso**: Sistema robusto de autenticação e autorização

## 🛠️ Tecnologias

### Frontend

- **React 19** com TypeScript
- **Vite** como bundler
- **Ant Design** para UI components
- **React Router** para roteamento
- **Axios** para requisições HTTP
- **Zod** para validação de dados

### Backend

- **NestJS** framework
- **TypeORM** para ORM
- **PostgreSQL** como banco de dados
- **JWT** para autenticação
- **Passport** para estratégias de autenticação

### Infraestrutura

- **Docker** e **Docker Compose**
- **Nginx** para servir o frontend em produção

## 🚀 Como Executar Localmente

### Pré-requisitos

- Docker e Docker Compose instalados
- Git

### Passo a Passo

1. **Clone o repositório com os submódulos**

```bash
git clone --recurse-submodules https://github.com/Arthu085/pharmasys-platform.git
cd pharmasys-platform
```

> **Nota:** Se você já clonou o repositório sem os submódulos, execute:
>
> ```bash
> git submodule update --init --recursive
> ```

2. **Configure as variáveis de ambiente**

```bash
cp .env.example .env
```

Edite o arquivo `.env` com suas configurações. As variáveis padrão já funcionam para desenvolvimento local.

3. **Inicie os containers**

```bash
docker-compose up -d
```

Isso irá inicializar:

- **Frontend** em: `http://localhost:80` (ou porta configurada em `FRONTEND_PORT`)
- **Backend** em: `http://localhost:3000` (ou porta configurada em `BACKEND_PORT`)
- **PostgreSQL** em: `localhost:5432` (ou porta configurada em `LOCAL_DB_PORT`)

4. **Aguarde a inicialização**

O backend executará automaticamente as migrations e seeds do banco de dados. Aguarde alguns segundos até que tudo esteja pronto.

5. **Acesse o sistema**

Abra seu navegador em `http://localhost:80` crie uma conta ou utilize as credenciais padrão para ter acesso em todas as telas:

```
Usuário: admin@gmail.com
Senha: 123456
```

### Parando o projeto

```bash
docker-compose down
```

Para remover também os volumes (dados do banco):

```bash
docker-compose down -v
```

## 📦 Executar Sem Docker

> **Nota:** Se você preferir executar o projeto sem Docker, será necessário configurar e executar cada serviço separadamente. Consulte os READMEs específicos:
>
> - **Frontend**: [pharmasys/README.md](https://github.com/Arthu085/pharmasys)
> - **Backend**: [pharmasys-api/README.md](https://github.com/Arthu085/pharmasys-api)

## 🌐 Testar em Produção

Você pode testar o sistema diretamente em produção sem precisar instalar nada localmente:

🔗 **[Acesse o PharmaSys Online](https://pharmasys-zh50.onrender.com/)**

## 📁 Estrutura do Projeto

```
pharmasys-platform/
├── pharmasys/              # Frontend React + Vite
│   ├── src/
│   │   ├── core/          # Configurações e utilitários core
│   │   ├── modules/       # Módulos da aplicação
│   │   └── shared/        # Componentes e utilitários compartilhados
│   └── Dockerfile
├── pharmasys-api/         # Backend NestJS
│   ├── src/
│   │   ├── core/          # Configurações core, database, filtros
│   │   ├── modules/       # Módulos da aplicação
│   │   └── shared/        # DTOs e utilitários compartilhados
│   └── Dockerfile
├── scripts/               # Scripts SQL de inicialização
│   └── init-db.sql
└── docker-compose.yml     # Orquestração dos containers
```

## 📚 Módulos Principais

- **Auth**: Autenticação e autorização
- **Company**: Gestão de empresas e unidades
- **User**: Gestão de usuários do sistema
- **Item**: Cadastro de itens/medicamentos
- **Batch**: Controle de lotes e validades
- **Stock Location**: Gestão de locais de armazenamento
- **Stock Balance**: Saldo de estoque por local
- **Stock Transfer**: Transferências entre locais
- **Inventory Entry**: Entradas de estoque
- **Inventory Exit**: Saídas de estoque
- **Item Dispensation**: Dispensação de medicamentos
- **Patient**: Cadastro de pacientes
- **Prescriptor**: Cadastro de prescritores/médicos
- **Dashboard**: Visualização das telas

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests.

## 👥 Autores

Desenvolvido por Arthur Ghizi

---

**Repositórios Relacionados:**

- [Frontend - pharmasys](https://github.com/Arthu085/pharmasys)
- [Backend - pharmasys-api](https://github.com/Arthu085/pharmasys-api)
