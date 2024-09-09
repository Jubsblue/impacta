## Pipeline com dados de voos
Este projeto tem como objetivo realizar o saneamento e a transformação dos dados de voos, utilizando um conjunto de funções para transformar e armazenar os dados em um banco SQLite.

## Funcionalidades
### app.py
- **Saneamento de Dados**: A função `data_clean` realiza o tratamento dos dados, incluindo a conversão de tipos, exclusão de valores nulos e a padronização de strings. Ela cria uma coluna de data de voo a partir de colunas de ano, mês e dia, e corrige a formatação das horas de partida e chegada.

- **Engenharia de Featuring**: A função `feat_eng` enriquece o DataFrame com novas colunas, como:
  - `tempo_voo_esperado`: Calcula o tempo de voo esperado com base nas colunas de data e hora.
  - `atraso`: Determina o atraso dos voos com relação ao tempo de voo esperado.
  - `dia_semana`: Extrai o dia da semana da data de voo.
  - `horario`: Classifica a hora de partida para categorização adicional.

- **Armazenamento em Banco de Dados**: A função `save_data_sqlite` realiza a conexão com um banco de dados SQLite e insere os dados tratados na tabela `nyflights`.

- **Recuperação de Dados**: A função `fetch_sqlite_data` valida a conexão com o banco de dados e recupera os registros de uma tabela específica, permitindo a visualização de alguns dados armazenados.

### utils.py
- **Leitura de Metadados**: A função `read_metadado` lê um arquivo CSV ou Excel contendo parâmetros de transformação dos dados e retorna um dicionário com as definições necessárias para o pipeline.

- **Saneamento de Dados**: A função `data_clean` realiza o tratamento dos dados, incluindo a conversão de tipos, exclusão de valores nulos e a padronização de strings. Ela cria uma coluna de data de voo a partir de colunas de ano, mês e dia, e corrige a formatação das horas de partida e chegada.

- **Exclusão de Nulos**: A função `null_exclude` remove observações do DataFrame que contêm valores nulos nas colunas-chave.

- **Renomeação de Colunas**: A função `select_rename` renomeia as colunas do DataFrame com base em um mapeamento fornecido.

- **Conversão de Tipos de Dados**: A função `convert_data_type` altera os tipos de dados das colunas de acordo com o mapeamento fornecido.

- **Padronização de Strings**: A função `string_std` aplica a padronização em colunas específicas para garantir consistência nos dados.

- **Validação de Nulos**: A função `null_check` valida se a quantidade de valores nulos em colunas específicas está dentro dos limites tolerados.

- **Verificação de Chaves**: A função `keys_check` valida as chaves do dataset, garantindo que não haja duplicatas nas colunas-chave.

- **Engenharia de Características**: A função `feat_eng` enriquece o DataFrame com novas colunas, como:
  - `tempo_voo_esperado`: Calcula o tempo de voo esperado com base nas colunas de data e hora.
  - `atraso`: Determina o atraso dos voos com relação ao tempo de voo esperado.
  - `dia_semana`: Extrai o dia da semana da data de voo.
  - `horario`: Classifica a hora de partida para categorização adicional.

- **Armazenamento em Banco de Dados**: A função `save_data_sqlite` realiza a conexão com um banco de dados SQLite e insere os dados tratados na tabela `nyflights`.

- **Recuperação de Dados**: A função `fetch_sqlite_data` valida a conexão com o banco de dados e recupera os registros de uma tabela específica, permitindo a visualização de alguns dados armazenados.
