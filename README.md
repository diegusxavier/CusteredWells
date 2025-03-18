![Static Badge](https://img.shields.io/badge/Python-yellow?logo=python) ![Static Badge](https://img.shields.io/badge/data%20science-green) ![Static Badge](https://img.shields.io/badge/machine%20learning-blue) ![Static Badge](https://img.shields.io/badge/Folium-brown)

# 🇧🇷 Mapeamento de zonas homólogas com base em dados hidroquímicos de um aquífero freático sujeito a contaminação por fossas em área peri-urbana de Campinas utilizando algoritmos de aprendizado de máquina
## Visão Geral
Esse repositório é referente ao meu projeto de Iniciação Científica da Universidade Estadual de Campinas (UNICAMP) e financiado pela PIBIC.

Para uma explicação detalhada do projeto, acesse a subpasta [docs](./docs) desse repositório. Nela, você encontrará o [Relatório Final da Iniciação](./docs/2023_03_PIBIC_RelatórioFinal_DiegoMachado.pdf) Científica e o [banner de apresenntação](./docs/2023_07_PIBIC_Congresso_DiegoXavier.pdf) no XXXI Congresso de Iniciação Científica da Unicamp.

## Funcionamento
O presente repositório deve ser rodado via Google Colab devido ao sistema de importação dos arquivos. Além disso, deve ser solicitado o acesso aos dados presentes na pasta do Google Drive onde estão salvos os projetos.

A pasta [raw](./data/raw) contém os documentos nos quais foram extraídos os dados utilizados nesse projeto. Esses dados foram cedidos pelo Instituto de Geociêncais da UNICAMP e, como foram entregues em diversos formatos, como `.pdf`, `.docx`, e `.xlsx`, precisaram ser formatados para uma base de dados unificada e em formato `.csv`. Essa base unificada completa e utilizada no projeto encontra-se em [tabela_coletas.csv](./data/processed/tabela_coletas.csv). Além disso, após uma filtragem feita com ajuda da professora orientadora (ver [Relatório Final da Iniciação](./docs/2023_03_PIBIC_RelatórioFinal_DiegoMachado.pdf) para mais detalhes), foi criada uma nova base com uma dimensão resuzida ([df_final.csv](./data/processed/df_final.csv)), que foi submetida aos algoritmos de aprendizado de máquina não supervisionado para agrupamento.

## Resumo da Introdução
As águas subterrâneas representam a maior parte da água disponível para o consumo humano e, no Estado de São Paulo, o uso dessa fonte  vem crescendo substancialmente nos últimos anos. Mediante a presente situação, mostra-se fundamental o monitoramento da qualidade das águas subterrâneas para preservá-las contra possíveis contaminações e evitar situações de risco à saúde da população que usa dessas águas.

A classificação da qualidade da água e de suas naturezas hidroquímicas são realizadas pelo conhecimento de especialistas. Porém, essa abordagem apresenta limitações para o estudo de sistemas subterrâneos complexos ou estudos em grande escala, regionais ou nacionais.

Nesse contexto de saúde pública, o presente projeto propõe aplicar, comparar e avaliar algoritmos aprendizado de máquina não-supervisionado para fazer um agrupamento dos dados coletados pelo Instituto de Geociências da Unicamp (IG) de águas subterrâneas da região do Piracambaia II, localizada ao norte do município de Campinas (SP), que foram objetos de estudo para a dissertação de mestrado Alencar. 

Além do estudo feito por Joana Alencar, o presente projeto tem como inpiração o artigo de Friedel et al. a respeito do uso de algoritmos de aprendizado de máquina não supervisionado para prever o caráter redox de águas subterrâneas.

## Resumo da Metodologia
Os dados foram coletados de difersas fontes disponibilizadas pelo Instituto de Geociências da UNICAMP, concatenados em planilhas no formato `.csv`, tratados mediante a necessidade, analisados por métodos de estatística descritivas e filtrados tanto com uma abordgem estatística quanto hidrogeoquímica, com ajuda da professora coorientadora do projeto, que é especialista na área. 

A partir da base de dados tratada, foram testados três algoritmos de aprendizado de máquina não supervisionado para classificação mediante a natureza hidroquímica da água, sendo eles:
- K-Means
- Self-Organizing Maps
- DBSCAN
E todos os algoritmos testados foram submetidos a métricas de avaliação dos algoritmos, sendo as métricas: Método da Silhueta, índice de Calinski-Harabasz e o índice de Davies–Bouldin.

## Resumo da Conclusão
Contudo, os testes resultaram em agrupamentos diferentes dentre os algoritmos utilizados, e também apresentaram resultados diferentes para um mesmo algoritmo quando analisado em períodos diferentes do ano. Portanto, os resultados apresentaram-se inconclusivos para o agrupamento das amostras de águas com base nos dados hidrogeoquímicos a partir da abordagem utilizada. Como hipótese, é discutível que o problema continha um pequeno espaço amostral, em relação à dimensão do problema, para o treinamento dos algoritmos de aprendizado de máquina utilizados. Outra hipótese levantada é a respeito da complexidade do problema, no qual uma análise hidrogeológica apenas pelas características físico-químicas das amostras não é suficiente para uma execução eficiente dos algoritmos.
