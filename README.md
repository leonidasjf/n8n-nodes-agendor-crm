<div align="center">

<table border="0">
<tr>
<td align="center" style="background-color: white; border-radius: 50%; padding: 10px;">
<img src="https://raw.githubusercontent.com/n8n-io/n8n/master/assets/n8n-logo.png" width="80" alt="n8n Logo" style="background-color: white; border-radius: 50%; padding: 5px;"/>
</td>
<td align="center" style="font-size: 30px; padding: 0 20px;">
<h2>+</h2>
</td>
<td align="center">
<img src="https://raw.githubusercontent.com/leonidasjf/n8n-nodes-agendor-crm/main/assets/agendorlogo.ico" width="80" alt="Agendor Logo"/>
</td>
</tr>
</table>

# 🚀 n8n-nodes-agendor-crm

**Node oficial do n8n para integração completa com o Agendor CRM**

[![npm version](https://badge.fury.io/js/n8n-nodes-agendor-crm.svg)](https://badge.fury.io/js/n8n-nodes-agendor-crm)
[![npm downloads](https://img.shields.io/npm/dm/n8n-nodes-agendor-crm.svg)](https://www.npmjs.com/package/n8n-nodes-agendor-crm)
[![GitHub stars](https://img.shields.io/github/stars/leonidasjf/n8n-nodes-agendor-crm.svg)](https://github.com/leonidasjf/n8n-nodes-agendor-crm)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

*Automatize seu CRM com workflows poderosos - Conecte o Agendor ao n8n e transforme seus processos de vendas!*

</div>

---

## ✨ Funcionalidades

### 📋 Recursos Suportados

- **📊 Organizações** - CRUD completo, busca e filtros
- **👥 Pessoas** - CRUD completo, busca e filtros
- **💼 Negócios** - CRUD completo, mudança de estágio, busca
- **✅ Tarefas** - CRUD completo, marcar como concluída
- **🏷️ Produtos** - CRUD completo
- **👤 Usuários** - Consulta de usuários e dados próprios
- **🎯 Funis** - Listagem de funis de vendas
- **📈 Estágios** - Listagem de estágios de negócios
- **🔧 Campos Personalizados** - Consulta de campos customizados
- **📊 Relatórios** - Analytics de vendas, pipeline e performance

### 🔧 Operações Disponíveis

#### Organizações
- ✅ Criar nova organização
- ✅ Buscar organização específica
- ✅ Listar múltiplas organizações
- ✅ Atualizar organização
- ✅ Deletar organização
- ✅ Buscar organizações

#### Pessoas
- ✅ Criar nova pessoa
- ✅ Buscar pessoa específica
- ✅ Listar múltiplas pessoas
- ✅ Atualizar pessoa
- ✅ Deletar pessoa
- ✅ Buscar pessoas

#### Negócios
- ✅ Criar novo negócio
- ✅ Buscar negócio específico
- ✅ Listar múltiplos negócios
- ✅ Atualizar negócio
- ✅ Deletar negócio
- ✅ Buscar negócios
- ✅ Mover negócio para outro estágio

#### Tarefas
- ✅ Criar nova tarefa
- ✅ Buscar tarefa específica
- ✅ Listar múltiplas tarefas
- ✅ Atualizar tarefa
- ✅ Deletar tarefa
- ✅ Marcar tarefa como concluída

#### Produtos
- ✅ Criar novo produto
- ✅ Buscar produto específico
- ✅ Listar múltiplos produtos
- ✅ Atualizar produto
- ✅ Deletar produto

#### Usuários
- ✅ Buscar usuário específico
- ✅ Listar múltiplos usuários
- ✅ Buscar dados do usuário atual

#### Funis e Configurações
- ✅ Listar funis de vendas
- ✅ Listar estágios de negócios
- ✅ Listar campos personalizados

#### Relatórios
- ✅ Análise de vendas
- ✅ Relatório de pipeline
- ✅ Relatório de performance

## 🚀 Instalação

### Via npm
```bash
npm install n8n-nodes-agendor-crm
```

### Via Community Nodes (n8n Cloud/Self-hosted)

1. Acesse **Settings** → **Community Nodes**
2. Clique em **Install a community node**
3. Digite: `n8n-nodes-agendor-crm`
4. Clique em **Install**

## 🔐 Configuração

### 1. Obter Token da API Agendor

1. Acesse sua conta no [Agendor](https://app.agendor.com.br/)
2. Vá em **Configurações** → **Integrações**
3. Clique em **Token de API**
4. Copie seu token

### 2. Configurar Credenciais no n8n

1. No n8n, vá para **Credentials**
2. Clique em **+ Add Credential**
3. Busque por **Agendor API**
4. Preencha:
   - **API Token**: Seu token copiado do Agendor
   - **API URL**: `https://api.agendor.com.br/v3` (padrão)

## 📖 Como Usar

### Exemplo Básico: Criar Organização

1. Adicione o node **Agendor** ao seu workflow
2. Configure:
   - **Credential**: Selecione sua credencial Agendor
   - **Resource**: Organization
   - **Operation**: Create
   - **Name**: Nome da organização
3. Execute o workflow

### Exemplo: Listar Negócios Recentes

1. Configure o node Agendor:
   - **Resource**: Deal
   - **Operation**: Get Many
   - **Filters**:
     - **Created After**: Data desejada
     - **Limit**: 50

### Exemplo: Buscar e Atualizar

1. **Node 1** - Buscar negócios:
   - **Resource**: Deal
   - **Operation**: Search
   - **Search Term**: "proposta"

2. **Node 2** - Atualizar negócios encontrados:
   - **Resource**: Deal
   - **Operation**: Update
   - **ID**: `{{$json.id}}`
   - **Additional Fields**: Campos a atualizar

## 🔍 Filtros e Parâmetros

### Filtros Comuns
- **Created After/Before**: Filtrar por data de criação
- **Updated After/Before**: Filtrar por data de atualização
- **Owner ID**: Filtrar por responsável
- **Return All**: Retornar todos os resultados (ignora limit)
- **Limit**: Limitar quantidade de resultados (1-500)

### Campos Suportados

#### Organizações
- Nome, CNPJ, Email, Telefone
- Website, Endereço, Cidade, Estado
- País, CEP, Descrição, Setor, Porte

#### Pessoas
- Nome, Email, Telefone, Celular
- CPF, Cargo, Organização, Aniversário
- Descrição

#### Negócios
- Título, Valor, Organização, Pessoa
- Funil, Estágio, Responsável
- Data Prevista, Descrição, Origem
- Probabilidade

#### Tarefas
- Título, Data de Vencimento, Tipo
- Descrição, Negócio Relacionado
- Organização, Pessoa, Responsável
- Prioridade

#### Produtos
- Nome, Preço, Descrição
- SKU, Categoria, Status

## 🎯 Casos de Uso

### 1. Sincronização de Leads
```
Webhook → Agendor (Create Organization) → Agendor (Create Person) → Agendor (Create Deal)
```

### 2. Follow-up Automático
```
Schedule → Agendor (Get Deals) → Filter (sem atividade) → Agendor (Create Task)
```

### 3. Relatório Diário
```
Schedule → Agendor (Sales Analytics) → Email/Slack (Send Report)
```

### 4. Integração E-commerce
```
E-commerce Webhook → Agendor (Create Deal) → Agendor (Move Stage) → Notification
```

### 5. Backup de Dados
```
Schedule → Agendor (Get All Data) → Google Sheets/Database (Store)
```

## 🔧 Desenvolvimento

### Pré-requisitos
- Node.js 18+
- pnpm 8+

### Setup Local
```bash
git clone https://github.com/leonidasfsilva/n8n-nodes-agendor-crm
cd n8n-nodes-agendor-crm
pnpm install
pnpm build
```

### Scripts Disponíveis
```bash
pnpm build      # Build do projeto
pnpm dev        # Watch mode para desenvolvimento
pnpm lint       # Lint do código
pnpm format     # Format do código
```

## 📚 Documentação da API

Este node segue a [documentação oficial da API do Agendor](https://api.agendor.com.br/docs/).

### Recursos Úteis
- [Documentação Agendor API](https://api.agendor.com.br/docs/)
- [n8n Community Nodes](https://docs.n8n.io/integrations/community-nodes/)
- [n8n Development Guide](https://docs.n8n.io/integrations/creating-nodes/)

## 🤝 Contribuição

Contribuições são bem-vindas! Por favor:

1. Fork o projeto
2. Crie sua feature branch (`git checkout -b feature/amazing-feature`)
3. Commit suas mudanças (`git commit -m 'Add amazing feature'`)
4. Push para a branch (`git push origin feature/amazing-feature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🆘 Suporte

- 🐛 **Issues**: [GitHub Issues](https://github.com/leonidasjf/n8n-nodes-agendor-crm/issues)
- 📖 **Documentação**: [Wiki](https://github.com/leonidasjf/n8n-nodes-agendor-crm/wiki)

## 🏷️ Keywords

- n8n
- agendor
- crm
- automation
- workflow
- integration
- sales
- pipeline
- leads

---

**Desenvolvido por [Leônidas Caldeira](https://github.com/leonidasjf)**