- 👋 Hi, I’m @Ggrighi1503
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Ggrighi1503/Ggrighi1503 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Importando as bibliotecas necessárias
import pandas as pd
from sqlalchemy import create_engine

# Conexão com o banco de dados (substitua com suas credenciais)
engine = create_engine('root@localhost:3306/BDContencioso)

# Carregando os dados da tabela (substitua 'sua_tabela' pelo nome da sua tabela)
df = pd.read_sql_query('SELECT * FROM processos', con=engine)

# Função para anonimizar dados sensíveis
def anonimizar_dados(df, colunas):
    for coluna in colunas:
        df[coluna] = 'ANONIMIZADO'  # Substitua por um método de anonimização adequado
    return df

# Lista de colunas com informações sensíveis
colunas_sensiveis = ['nome', 'email', 'cpf']

# Anonimizando os dados
df_anonimizado = anonimizar_dados(df, colunas_sensiveis)

# Salvando os dados anonimizados em um novo arquivo CSV
df_anonimizado.to_csv('dados_anonimizados.csv', index=False)

# Carregando os dados anonimizados no Power BI
# No Power BI, use a opção 'Obter Dados' e selecione 'Arquivo CSV' para carregar 'dados_anonimizados.csv'
