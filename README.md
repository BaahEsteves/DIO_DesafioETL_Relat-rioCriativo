# Integração de Banco de Dados na Azure com Power BI

Este repositório contém informações sobre como realizar a integração de um banco de dados MySQL hospedado na Azure com o Power BI, incluindo transformações e mesclagens de dados.

## Configuração do Ambiente

1. Criação de uma instância na Azure para MySQL.
2. Criação do Banco de Dados com base em um Script disponibilizado.

## Integração do Power BI com MySQL na Azure

Explicação sobre como configurar o Power BI para se conectar ao banco de dados MySQL hospedado na Azure.

## Transformações de Dados

### Tabela Departamento

- Exclusão das colunas desnecessárias.
- Alteração dos Cabeçalhos para melhor entendimento da estrutura do banco de dados.
- Verificação dos tipos de dados.

### Tabela Dependente

- Exclusão das colunas desnecessárias.
- Alteração dos Cabeçalhos para melhor entendimento da estrutura do banco de dados.
- Verificação dos tipos de dados.

### Tabela Localização Departamento

- Exclusão das colunas desnecessárias.
- Alteração dos Cabeçalhos para melhor entendimento da estrutura do banco de dados.
- Verificação dos tipos de dados.

### Tabela Colaborador

- Exclusão das colunas desnecessárias.
- Alteração dos Cabeçalhos para melhor entendimento da estrutura do banco de dados.
- Separação da coluna de endereço usando o delimitador "-".
- Mudança da coluna Salário para decimal fixo.

### Tabela Projeto

- Exclusão das colunas desnecessárias.
- Alteração dos Cabeçalhos para melhor entendimento da estrutura do banco de dados.
- Verificação dos tipos de dados.

### Tabela Demanda

- Exclusão das colunas desnecessárias.
- Alteração dos Cabeçalhos para melhor entendimento da estrutura do banco de dados.
- Verificação dos tipos de dados.

## Mesclagens de Dados

- Criação da tabela "Demanda por Projeto": Mesclagem como nova consulta de projetos e demanda, e agrupamento por nome de projeto para somar a quantidade total gasta em cada projeto.
- Criação da tabela "Colaborador por Departamento": Mesclagem como nova consulta da tabela Colaborador com Departamento pelo número de ID do departamento, mantendo apenas as colunas relevantes.
- Mesclagem das Colunas Nome e Sobrenome dos Colaboradores: Junção das duas colunas com o delimitador "espaço".
- Criação da tabela "Colaborador por Gerente": Mesclagem como nova consulta da tabela Colaborador com Colaborador pelo número de ID do Gerente e ID do Colaborador, mantendo apenas as colunas relevantes.
- Mesclagem das Colunas Nome de Departamento e Local criando a coluna "departamento-local" para ser único, usando delimitador "-".
- Agrupamento de dados para saber quantos colaboradores existem por gerente, com exclusão da linha que indica um colaborador sem gerente.
- Exclusão das colunas desnecessárias de cada tabela que não serão usadas no relatório.

## Considerações

- O valor nulo presente na tabela colaborador na coluna se deve ao fato de ele ser um gerente e não possuir um cargo acima dele, portanto ele é o único colaborador sem gerente.
- A operação de mesclagem é usada para adicionar informações de uma tabela a outra, com base em algum critério de correspondência, nesses casos as colunas estão em tabelas distintas e para conseguir agrupá-las sem criar linhas com valores sem conexão com as existentes deve ser usado mesclagem ao invés de atribuir.
