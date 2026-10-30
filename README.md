# Atividade Prática — Pipeline de Limpeza Completo
Atividade da Aula 10 da disciplina de “Análise e Ciência de Dados” do curso “Ciência de Dados” do IFRN.

<p align="center">
  <img width="626" height="469" src="https://miro.medium.com/v2/1*SIghSwqgQCz2dsT9TVOYPw.jpeg">
</p>

**Descrição**<br>
Este repositório contém a atividade prática da aula 10 da disciplina de “Análise e Ciência de Dados” do curso “Ciência de Dados” do IFRN. Neste projeto aplicamos um pipeline ETL completo de limpeza e preparação de dados a um conjunto sintético de exames laboratoriais de uma rede hospitalar fictícia do RN, com problemas de qualidade inseridos de propósito.

**Objetivo**<br>
Aplicar um pipeline de limpeza completo ao arquivo exames_laboratoriais.csv (155 exames sintéticos) e entregar um dataset limpo e um notebook documentado, aplicando os conceitos vistos em aula: diagnóstico de qualidade, transformação de tipos, padronização, tratamento de valores inválidos e ausentes, engenharia de atributos, codificação de variáveis categóricas, validação e exportação com dicionário de dados.

Requisitos mínimos:

1 - Extract e diagnóstico: tipos, ausentes, duplicatas e categorias.<br>
2 - Remoção de duplicatas, conferindo que id_exame ficou único.<br>
3 - Transformação de tipos: data_coleta (dois formatos) em data e resultado (“84,2”) em número.<br>
4 - Padronização de sexo, prioridade e laboratorio.<br>
5 - Código 999 em resultado tratado como ausente; imputação do resultado pela mediana do mesmo tipo de exame e da idade pela mediana.<br>
6 - Engenharia de atributos: faixa_etaria (pd.cut), mes_coleta e alterado (fora da faixa de referência).<br>
7 - Codificação: prioridade_cod ordinal e one-hot de tipo_exame.<br>
8 - Validação com assert.<br>
9 - Exportação do CSV limpo e dicionário de dados.<br>
10 - Conclusão sobre problemas, decisões e um achado.<br>

**Dados**<br>
Este exercício usou o arquivo exames_laboratoriais.csv, um conjunto de dados sintético (sorteado por script com semente fixa) que imita exames laboratoriais de uma rede hospitalar fictícia do RN. Nenhum registro corresponde a um paciente real. Os problemas de qualidade (duplicatas, formatos misturados, grafias inconsistentes, ausentes e código sentinela) foram inseridos de propósito.

**Conclusão**<br>
- O dataset bruto tinha 155 exames e 10 colunas, com 5 linhas duplicadas, data_coleta em dois formatos (ISO e dd/mm/aaaa), resultado como texto com vírgula decimal, grafias inconsistentes em sexo, prioridade e laboratorio, 6 idades ausentes (após remover duplicatas) e 4 resultados com o código 999 (“amostra não processada”). Depois do pipeline, o dataset final tem 150 linhas e 18 colunas, sem valores ausentes.

- As principais decisões foram: remover as duplicatas; converter os tipos; padronizar as categorias; tratar o 999 como ausente e imputar resultado pela mediana do mesmo tipo de exame (porque glicemia, colesterol, creatinina e hemoglobina têm escalas muito diferentes) e idade pela mediana geral. Só o código 999 inflava a média de resultado de 87,75 para 112,05. O resultado foi validado com assert e documentado com um dicionário de dados.

- Com os dados limpos, um achado foi que 58% dos exames de colesterol total estavam fora da faixa de referência, contra 36% da glicemia, 14% da creatinina e apenas 4% da hemoglobina. Como os dados são sintéticos e as faixas de referência são simplificadas (apenas para fins didáticos), esse achado não tem valor clínico.
  
**Componente**<br>

- Joelson Ferreira - <a href="https://www.linkedin.com/in/joelsons/" target="_blank">LinkedIn</a>
  
**Professor**<br>

- Placido Antonio de Souza Neto - [LinkedIn](https://www.linkedin.com/in/placidoneto/)

**Links úteis**<br>

- Projeto - [GitHub](https://github.com/Joelson-Ferreira/Laboratorio-Pipeline-de-Limpeza-Completo)
  
<br>**ATENÇÃO: Por favor, lembre-se de que os resultados desta trabalho são para fins acadêmicos, e não representa verdade absoluta. Use essas informações com discernimento e considere outras fontes e contexto antes de tirar conclusões definitivas.**
