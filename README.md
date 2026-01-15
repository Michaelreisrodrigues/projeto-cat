# 🛡️ Dashboard de Análise de Segurança do Trabalho (CAT)
![Capa do Dashboard](capa_projeto.png.png) 
# 📖 Visão Geral
Este projeto apresenta uma análise técnica e estratégica das Comunicações de Acidente de Trabalho (CAT). O grande diferencial é a integração de um pipeline de dados em Python para tratar inconsistências da base bruta, fornecendo dados limpos e confiáveis para o dashboard final.


# 🎯 Objetivo
Transformar registros brutos em inteligência estratégica para:

Identificar setores e perfis de trabalhadores com maior vulnerabilidade.

Analisar a severidade das lesões e os agentes causadores recorrentes.

Corrigir falhas de preenchimento e tratar dados vazios para uma análise precisa.

# 📂 Estrutura do Projeto 
A organização do repositório segue a arquitetura abaixo, conforme visualizado no VS Code:

├── 📁 .venv                        # Ambiente virtual Python
├── 📁 Data
│   ├── 📁 processed                # Dados limpos para o Power BI
│   │   └── CAT_Novembro_Final_BI.csv
│   └── 📁 raw                      # Base de dados original (bruta)
│       └── D.SDA.PDA.005.CAT.202511.csv
├── 📁 notebooks
│   └── limpeza.ipynb               # Jupyter Notebook com o pipeline de ETL
├── 📄 .gitignore                   # Arquivos ignorados pelo Git
├── 📄 README.md                    # Documentação do projeto
└── 📄 requirements.txt             # Bibliotecas necessárias (Pandas,Numpy)

# 🛠️ Tecnologias e Processos
1. Engenharia de Dados com Python (Pandas & Numpy)
O processamento (ETL) foi realizado no VS Code com Python, garantindo que o Power BI recebesse dados prontos para análise. O script executa:

Mapeamento de Dicionário: Correção de nomes cortados e erros de caracteres (ex: (Exceto Punho Ou" corrigido para "Mão")).

Saneamento de Outliers: Regra de negócio aplicada para remover idades inconsistentes (menores de 14 ou maiores de 100 anos).

Normalização: Padronização de textos para Title Case e remoção de espaços extras.

2. Inteligência de Dados com Power BI & DAX
Cálculos Avançados: Criação de medidas DAX para normalizar a idade média (convertendo meses para anos).

Tratamento de Vazio (Blank): Implementação de lógica COALESCE e IF(ISBLANK()) para garantir que os cartões exibam 0 em vez de ficarem em branco em filtros sem dados.

UX/UI Profissional: Interface desenvolvida com capa personalizada (PowerPoint), utilizando uma paleta de cores voltada ao setor de Segurança do Trabalho.

# 🐍 Trecho do Pipeline de Limpeza (Python)
Para garantir a qualidade visual, o seguinte tratamento foi aplicado via Pandas:

Python

# Mapeamento para correção de nomes cortados na base bruta
mapeamento_limpeza = {
    'Mão (Exceto Punho Ou)': 'Mão',
    'Pé (Exceto Artelhos)': 'Pé',
    'Atividade De Atendi': 'Atendimento Hospitalar'
}

# Substituição segura e limpeza de dados
df_clean = df_clean.replace(mapeamento_limpeza, regex=False)
# 📊 Principais Indicadores
Total de Acidentes: Volume total de ocorrências registradas.

Média de Idade: Perfil etário médio dos acidentados.

Perfil Demográfico: Distribuição por gênero e faixa etária.

Análise de Severidade: Top agentes causadores e tipos de lesão.

Desenvolvido por Michael Reis Rodrigues LinkedIn | michaelreisrodrigues@gmail.com
