# Case-Estabelecimentos

Análise e tratamento de dados de estabelecimentos cadastrados no portal da Receita Federal.

Arquivo escolhido: Dados Abertos CNPJ ESTABELECIMENTO 01 (disponível em: https://www.gov.br/receitafederal/pt-br/assuntos/orientacao-tributaria/cadastros/consultas/dados-publicos-cnpj)

Arquivos na pasta Código:

1-Pipeline exec.ipynb
  Jupyter Notebook com carregamento de dados e chaada da pipeline de tratamento dos dados
  
2- Pipeline.py
  Arquivo cmo definições das funções utilizadas na pipeline
  
Outputs: <br />
 1. Arquivos CSV: <br />
    - Finais.csv :<br />
    
      Porcentagem Ativos : Porcentagem de empresas ativas ( Situação Cadastral ). Resposta **item 4a do desafio**
      Total < 5km : Total de empresas que se localizam dentro de um raio de 5km do CEP 01422000. Resposta **item 4c** <br />
    - TabelaAno.csv : <br />
    
      Total de empresas do setor de restaurantes que foram abertas em cada ano. reposta **item 4b** <br />
    - TabelaCNAE.csv :<br />
   
      Tabela de correlação de CNAE Primario (Cnae1) e CNAE Secundário (Cnae 2). A coluna 'total' informa quantas ocorrências de cada cobinação de CNAE existem. Resposta **item 4d** <br />
2. Arquivo Excel TabelaFinal.xlsx dividido em sheets. Agrega todos os resultados dos arquivos CSV em um unico arquivo Excel:<br />
    - DadosAtivos: <br />
     
      Resultados referentes ao arquivo Finais.csv <br />
    - TabelaAno: <br />
    
      Resultados referentes ao arquivo TabelaAno.csv <br />
    - TabelaCNAE : <br />
    
      Resultados referentes ao arquivo TabelaCNAE.csv <br />
    
   
 Observações:
  - O tempo necessário para a a plicação da pipeline ao arquivo de dados completo é marjoritariamente dominado pela etapa de geocode, uma vez que o provedor gratuito utilizado permite apenas uma query de endereço por segundo. Para minimizar esse tempo, foi filtrado os endereços a serem consultados por uma lista de CEP's próximos ao local alvo. Também foi utilizado apenas noes de logradouros únicos.
    
