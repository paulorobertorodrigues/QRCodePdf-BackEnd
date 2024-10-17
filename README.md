QRCodePDF - Backend
Este é o backend da aplicação QRCodePDF, que oferece serviços de autenticação, geração de certificados e armazenamento de dados de empregados. Ele utiliza tecnologias como Express, MySQL e JWT para gerenciamento de usuários e autenticação, além de permitir a criação de PDFs a partir de informações cadastradas.

Tecnologias Utilizadas
Node.js: Ambiente de execução para o JavaScript no backend.
Express: Framework web para construção de APIs e rotas.
MySQL: Banco de dados relacional utilizado para armazenamento de informações.
JWT (JsonWebToken): Utilizado para autenticação e controle de acesso seguro.
dotenv: Gerenciamento de variáveis de ambiente.
Cors: Controla as origens permitidas para fazer requisições ao backend.
html2pdf.js: Biblioteca para converter HTML em arquivos PDF.
Estrutura do Projeto
bash
Copiar código
root/
│
├── Routes/
│   ├── AdminRoute.js         # Rota de login para administradores
│
├── utils/
│   ├── db.js                 # Conexão com o banco de dados MySQL
│
├── .env                      # Arquivo de variáveis de ambiente (configuração de banco de dados e outras variáveis)
├── index.js                  # Arquivo principal que inicia o servidor
├── package.json              # Dependências e scripts do projeto
└── README.md                 # Documentação do projeto
Configuração
Pré-requisitos
Antes de começar, certifique-se de ter os seguintes softwares instalados:

Node.js (v14 ou superior)
MySQL
Instalação
Clone o repositório:
bash
Copiar código
git clone https://github.com/paulorobertorodrigues/QRCodePdf-BackEnd.git
Navegue até o diretório do projeto:
bash
Copiar código
cd QRCodePdf-BackEnd
Instale as dependências:
bash
Copiar código
npm install
Configure as variáveis de ambiente:
Crie um arquivo .env na raiz do projeto com as seguintes variáveis:

bash
Copiar código
HOST=localhost
USER=root
PASSWORD=sua_senha
DATABASE=nome_do_banco
PORT=3000
JWT_SECRET=jwt_secret_key
Execute o servidor:
bash
Copiar código
npm start
O servidor estará rodando em http://localhost:3000.

Rotas
1. Rota de Autenticação de Admin (/auth/adminlogin)
POST /auth/adminlogin

Endpoint para realizar login como administrador.

Body:

json
Copiar código
{
  "email": "admin@example.com",
  "password": "sua_senha"
}
Resposta:

Em caso de sucesso, retorna um token JWT que é armazenado em um cookie para autenticação.
Em caso de erro, retorna uma mensagem indicando a falha.
2. CRUD de Empregados
POST /create: Cria um novo registro de empregado no banco de dados.
GET /empregados: Retorna todos os empregados cadastrados.
PUT /update: Atualiza as informações de um empregado existente.
DELETE /delete/:id: Deleta um empregado com base no ID.
Banco de Dados
O projeto utiliza MySQL para armazenamento de dados. Certifique-se de criar um banco de dados e executar os scripts SQL necessários para criar a tabela empregados.

Exemplo de estrutura da tabela:

sql
Copiar código
CREATE TABLE empregados (
  id INT AUTO_INCREMENT PRIMARY KEY,
  data DATE,
  revisao VARCHAR(255),
  codigo VARCHAR(255),
  validade DATE,
  responsavel VARCHAR(255),
  registro VARCHAR(255)
);
Funcionalidades Futuras
Melhorias no sistema de geração de PDFs.
Adição de novos campos e validações para o cadastro de empregados.
Integração com o frontend para melhor experiência do usuário.
Contribuição
Se você quiser contribuir com este projeto:

Faça um fork do repositório.
Crie uma nova branch: git checkout -b minha-feature
Faça as alterações e adicione os commits: git commit -m 'Adicionando minha feature'
Envie para o seu repositório fork: git push origin minha-feature
Crie um pull request no repositório original.
Autor
Paulo Roberto Rodrigues

GitHub
(https://github.com/paulorobertorodrigues)
