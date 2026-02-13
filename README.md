📚 API de Livraria - Alura (Modo Carreira Node.js)
Esta API foi desenvolvida como parte da formação de Node.js da Alura, focando em boas práticas de arquitetura, manipulação de dados com MongoDB e criação de middlewares reutilizáveis. A aplicação gerencia um catálogo de livros e autores, permitindo operações completas de armazenamento e consultas complexas.

🚀 Funcionalidades

🛠️ CRUD Completo
A API expõe endpoints para gerenciar o ciclo de vida dos recursos:
Livros: Cadastro, listagem, atualização e exclusão.
Autores: Cadastro, listagem, atualização e exclusão de escritores.

🔍 Busca Avançada
Implementação de filtros dinâmicos na rota /livros/busca, permitindo localizar obras por:
Título: Busca por termos parciais (Regex).
Editora: Filtro exato por nome da editora.
Faixa de Preço: Filtragem entre valores mínimos e máximos ($gte e $lte).
Nome do Autor: Localização de livros baseada na identificação do autor vinculado.

📄 Paginação e Ordenação
Integração de um Middleware de Paginação global que pode ser acoplado a qualquer rota de listagem:
Controle de Fluxo: Uso dos métodos .skip() e .limit() do Mongoose.
Ordenação Dinâmica: Permite ordenar por qualquer campo (ex: _id, titulo) de forma crescente ou decrescente via query strings.
Uso via URL: ?limite=5&pagina=1&ordenacao=titulo:-1.

⚠️ Tratamento de Erros
Centralização da lógica de exceções em um middleware específico:
Erros de Cast: Tratamento para IDs inválidos do MongoDB.
Erros de Validação: Captura de campos obrigatórios não preenchidos.
Erro 404: Gerenciamento de recursos não encontrados.
Classes de Erro Customizadas: Estrutura extensível para diferentes códigos de status HTTP.

🛠️ Tecnologias Utilizadas
Node.js: Ambiente de execução.
Express: Framework para gerenciamento de rotas e middlewares.
MongoDB & Mongoose: Banco de dados NoSQL e modelagem de objetos.
Postman: Testes de endpoints e fluxos de requisição.