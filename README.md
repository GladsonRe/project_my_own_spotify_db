# Banco de Dados de Uso do Spotify

Bem-vindo ao meu projeto de Banco de Dados de Uso do Spotify! Este projeto tem como objetivo coletar e armazenar dados sobre o meu uso do Spotify, como as músicas que escuto com mais frequência, os artistas que mais ouço e as minhas playlists favoritas.

## Ferramentas Utilizadas

O projeto foi desenvolvido utilizando as seguintes ferramentas:

- **API do Spotify**: utilizada para coletar informações sobre o uso do Spotify
- **Python**: linguagem de programação utilizada para automatizar a coleta de dados e manipulação dos dados
- **Pandas e NumPy**: bibliotecas utilizadas para manipulação dos dados
- **Spotipy**: biblioteca utilizada para acessar a API do Spotify
- **Sqlite3**: biblioteca utilizada para manipulação do banco de dados
- **SQLite**: banco de dados utilizado para armazenar os dados coletados
- **DB Designer**: ferramenta utilizada para modelar o banco de dados
- **Conceitos de Modelagem de Dados**: aprendidos com o livro do Osvaldo de Sordi

## Funcionamento do Projeto

O projeto é executado por meio de dois scripts:
- **aquisicao_de_dados**: realiza a aquisição das ultimas músicas ouvidas, há um limite de apenas as ultimas 50 músicas (o que é uma pena). O script utiliza a biblioteca Spotipy para acessar a API do Spotify e coletar as informações sobre o uso do Spotify.
- **geracao_das_bases**: esse script é responsável por manipular os dados brutos originados no script aquisicao_de_dados e armazená-los em um banco de dados SQLite.
- **SQL_CREATE_TABLES_FUN**: esse arquivo de texto, contém os scripts SQL para criação das tabelas do banco de dados.

## Premissas adotadas

Eu precisei adotar algumas premissas básicas para o meu projeto. Acredito que algumas escolhas poderiam ter sido diferentes a depender do contexto, então criei essa seção pra explicar o motivo delas:
- **CHAVES DAS TABELAS**: Optei por criar chaves próprias para o meu banco apenas a nível de prática. Acho que nesse caso a melhor solução seria usar o próprio sistema de IDs criado pelo spotify. As chaves originais foram mantidas nas tabelas.
- **RELACIONAMENTO 1:N (T_ALBUM x T_ARTISTS)**: Essa aqui foi uma observação que surgiu durante o desenvolvimento do projeto... Quando falamos de música, não é tão comum termos um album assinado por mais de um artista (mas é possível). De forma geral, em música é bem mais comum (através dos feats). Diante disso, optei por deixar a definição de que um artista pode ter vários albums, mas um album pertence a um único artista (1:N). Bem, esse erro de percurso vai me economizar algum espaço, mas pode gerar uma informação imprecisa.
- **REGISTROS DUPLICADOS ?**: O script de geração das bases possui controle de registros duplicados

## Como Utilizar o Projeto

Para utilizar o projeto, é necessário ter uma conta no Spotify e uma chave de acesso à API do Spotify. Em seguida, é preciso clonar o repositório do GitHub para o seu computador e instalar as bibliotecas necessárias por meio do virtual environment (venv). Após a instalação das bibliotecas, basta executar o script em Python para realizar a coleta de dados e armazenamento no banco de dados SQLite. Não esqueça de criar as tabelas com o script SQL disponibilizado!!!

## Contribuições

Sinta-se à vontade para explorar este repositório e contribuir com sugestões ou melhorias para o projeto. Qualquer ajuda é bem-vinda!

## Implementações futuras

- Uso do Airflow para orquestração das consultas
