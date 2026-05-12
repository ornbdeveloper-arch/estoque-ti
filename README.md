# 📦 Sistema de Gestão de Estoque de TI

Um sistema web completo para gerenciamento de estoque de equipamentos de TI, permitindo cadastro de produtos, controle de entrada/saída, relatórios detalhados e geração automática de pedidos de compra em Excel.

---

## 🎯 Funcionalidades

### ✅ Cadastro de Produtos
- Registrar novos produtos com:
  - Número de série
  - Modelo
  - Código de barras
  - ID único
  - Quantidade em estoque

### ✅ Controle de Movimentação
- **Entrada de itens** - Adicionar produtos ao estoque
- **Saída de itens** - Retirar produtos para uso
- Histórico completo de movimentações
- Rastreamento de itens

### ✅ Relatórios
- Relatório de itens em estoque
- Relatório de itens em uso
- Visualização de quantidades e detalhes
- Exportação de dados

### ✅ Pedido de Compras
- Gerar automaticamente pedido em Excel
- Incluir itens que precisam reposição
- Definir quantidades a comprar
- Facilitar comunicação com setor de compras

---

## 🛠️ Tecnologias Utilizadas

### Backend
- **Python 3.8+** - Linguagem principal
- **Flask** - Framework web leve e flexível
- **Flask-SQLAlchemy** - ORM para banco de dados
- **Flask-CORS** - Suporte a requisições cross-origin
- **SQLite** - Banco de dados local
- **OpenPyXL** - Geração de arquivos Excel

### Frontend
- **HTML5** - Estrutura das páginas
- **CSS3** - Estilização responsiva
- **JavaScript Vanilla** - Interatividade
- **Fetch API** - Comunicação com backend

### Ferramentas
- **Git** - Controle de versão
- **Virtual Environment** - Isolamento de dependências Python

---

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- **Python 3.8+** → [Download](https://www.python.org/downloads/)
- **Git** → [Download](https://git-scm.com/)
- **Navegador moderno** (Chrome, Firefox, Edge)

---

## 🚀 Como Instalar e Executar

### 1. Clonar o Repositório

```bash
git clone https://github.com/seu-usuario/estoque-ti-sistema.git
cd estoque-ti-sistema
```

### 2. Criar Ambiente Virtual

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**Mac/Linux:**
```bash
python -m venv venv
source venv/bin/activate
```

Você saberá que funcionou quando ver `(venv)` no terminal.

### 3. Instalar Dependências

```bash
pip install -r requirements.txt
```

### 4. Executar a Aplicação

```bash
python run.py
```

A aplicação estará disponível em: **http://localhost:5000**

---

## 📁 Estrutura do Projeto

```
estoque-ti-sistema/
├── app/                          # Código principal da aplicação
│   ├── __init__.py              # Inicialização do Flask
│   ├── main.py                  # Arquivo principal
│   ├── database.py              # Configuração do banco de dados
│   │
│   ├── models/                  # Modelos de dados
│   │   ├── __init__.py
│   │   ├── produto.py           # Modelo de Produto
│   │   └── movimentacao.py      # Modelo de Movimentação
│   │
│   ├── routes/                  # Rotas das APIs REST
│   │   ├── __init__.py
│   │   ├── produto_routes.py    # Endpoints de produtos
│   │   ├── movimentacao_routes.py # Endpoints de movimentações
│   │   └── relatorio_routes.py  # Endpoints de relatórios
│   │
│   └── services/                # Lógica de negócio
│       ├── __init__.py
│       ├── produto_service.py   # Serviço de produtos
│       ├── movimentacao_service.py # Serviço de movimentações
│       └── relatorio_service.py # Serviço de relatórios
│
├── frontend/                    # Interface web
│   ├── index.html              # Página inicial
│   ├── cadastro.html           # Cadastro de produtos
│   ├── movimentacao.html       # Entrada/Saída de itens
│   ├── relatorios.html         # Visualização de relatórios
│   ├── css/
│   │   └── style.css           # Estilos globais
│   └── js/
│       ├── api.js              # Funções de requisição à API
│       ├── produto.js          # Lógica de produtos
│       ├── movimentacao.js     # Lógica de movimentações
│       └── relatorio.js        # Lógica de relatórios
│
├── run.py                       # Script para iniciar servidor
├── config.py                    # Configurações da aplicação
├── requirements.txt             # Dependências Python
├── .gitignore                   # Arquivos ignorados pelo Git
└── README.md                    # Este arquivo
```

---

## 🔌 API REST - Endpoints

### Produtos

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| `GET` | `/api/produtos` | Listar todos os produtos |
| `GET` | `/api/produtos/<id>` | Obter produto específico |
| `POST` | `/api/produtos` | Cadastrar novo produto |
| `PUT` | `/api/produtos/<id>` | Atualizar produto |
| `DELETE` | `/api/produtos/<id>` | Deletar produto |

### Movimentações

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| `GET` | `/api/movimentacoes` | Listar todas movimentações |
| `POST` | `/api/movimentacoes/entrada` | Registrar entrada de item |
| `POST` | `/api/movimentacoes/saida` | Registrar saída de item |

### Relatórios

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| `GET` | `/api/relatorios/estoque` | Relatório de estoque |
| `GET` | `/api/relatorios/uso` | Relatório de itens em uso |
| `GET` | `/api/relatorios/excel` | Gerar pedido em Excel |

---

## 📖 Como Usar

### 1. Acessar a Aplicação
Abra seu navegador e acesse: **http://localhost:5000**

### 2. Cadastrar Produtos
- Vá para a aba **"Cadastro"**
- Preencha os dados do produto (série, modelo, código, ID)
- Clique em **"Salvar"**

### 3. Controlar Movimentação
- Vá para **"Movimentação"**
- Escolha se é **Entrada** ou **Saída**
- Selecione o produto e quantidade
- Registre a operação

### 4. Ver Relatórios
- Acesse a aba **"Relatórios"**
- Visualize itens em estoque e em uso
- Exporte dados se necessário

### 5. Gerar Pedido de Compras
- Na aba **"Relatórios"**, clique em **"Gerar Pedido"**
- Um arquivo Excel será baixado
- Envie para o setor de compras

---

## 🔧 Configuração

### Arquivo `config.py`

```python
import os

class Config:
    # Banco de dados
    SQLALCHEMY_DATABASE_URI = 'sqlite:///estoque.db'
    SQLALCHEMY_TRACK_MODIFICATIONS = False
    
    # Flask
    DEBUG = True
    SECRET_KEY = 'sua-chave-secreta-aqui'
```

---

## 📊 Modelo de Dados

### Produto
```python
{
    "id": 1,
    "numero_serie": "ABC123456",
    "modelo": "Dell Inspiron 15",
    "codigo_barras": "1234567890123",
    "id_produto": "DELL-001",
    "quantidade": 5,
    "data_criacao": "2024-01-15"
}
```

### Movimentação
```python
{
    "id": 1,
    "produto_id": 1,
    "tipo": "entrada",  # ou "saida"
    "quantidade": 2,
    "observacoes": "Compra inicial",
    "data_movimentacao": "2024-01-15T10:30:00"
}
```

---

## 🐛 Troubleshooting

### Erro: "python: command not found"
- Python não está instalado ou não está no PATH
- Solução: Instale Python e marque "Add to PATH"

### Erro: "No module named 'flask'"
- Ambiente virtual não está ativado
- Solução: Execute `venv\Scripts\activate` (Windows) ou `source venv/bin/activate` (Mac/Linux)

### Erro: "Address already in use"
- Porta 5000 já está em uso
- Solução: Mude a porta em `run.py` ou encerre o processo usando a porta

### Banco de dados não carrega
- Arquivo `estoque.db` corrompido
- Solução: Delete o arquivo `.db` e reinicie (criará novo)

---

## 🚀 Próximas Melhorias

- [ ] Autenticação de usuários
- [ ] Dashboard com gráficos
- [ ] Filtros avançados de relatórios
- [ ] Backup automático de dados
- [ ] Notificações de baixo estoque
- [ ] Integração com sistemas de compra
- [ ] App mobile
- [ ] Testes automatizados

---

## 📝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Faça um Fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

---

## 📄 Licença

Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.

---

## 👤 Autor

**Seu Nome**
- GitHub: [@seu-usuario](https://github.com/seu-usuario)
- Email: seu.email@exemplo.com

---

## 🤝 Suporte

Se tiver dúvidas ou problemas:

1. Verifique a seção **Troubleshooting**
2. Abra uma [Issue](https://github.com/seu-usuario/estoque-ti-sistema/issues)
3. Entre em contato por email

---

## 📚 Recursos Úteis

- [Flask Documentation](https://flask.palletsprojects.com/)
- [SQLAlchemy ORM Tutorial](https://docs.sqlalchemy.org/)
- [MDN Web Docs](https://developer.mozilla.org/)
- [OpenPyXL Guide](https://openpyxl.readthedocs.io/)

---

## 🎉 Agradecimentos

Obrigado por usar o Sistema de Gestão de Estoque de TI!

**Made with ❤️ by Seu Nome**

---

## 📞 Roadmap

### v1.0 (Atual)
- ✅ Cadastro de produtos
- ✅ Controle de entrada/saída
- ✅ Relatórios básicos
- ✅ Geração de Excel

### v1.1 (Próximo)
- [ ] Busca e filtros avançados
- [ ] Previsão de falta de estoque
- [ ] Histórico detalhado

### v2.0 (Futuro)
- [ ] Sistema de usuários
- [ ] Dashboard analítico
- [ ] Mobile app
- [ ] API GraphQL

---

**Última atualização:** Janeiro de 2024

Aproveite! 🚀