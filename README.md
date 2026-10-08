# Análise do mercado de vagas de TI



Projeto de análise de dados em Excel para praticar limpeza, tratamento, análise exploratória e documentação, usando um conjunto real de vagas de emprego de TI. O escopo está em expansão: o que começou como um mini projeto está sendo ampliado.



## Dataset



- Arquivo original: `data/raw/final\_data.csv`

- Fonte: [LinkedIn Tech Jobs (Kaggle)](https://www.kaggle.com/datasets/joebeachcapital/linkedin-jobs)

- Conteúdo: 811 vagas de TI de 11 empresas, com localização, senioridade, tipo de contrato, número de candidatos e tecnologias exigidas por vaga.



## Pergunta da análise



Quais tecnologias são mais exigidas nas vagas de TI e como essa demanda varia por empresa, categoria de cargo e nível de senioridade?



## Tratamento dos dados



- As colunas `Level` e `Involvement` tinham nomes trocados em relação ao conteúdo e foram colocadas na ordem correta.

- Espaços extras no início dos textos foram removidos.

- 126 vagas com `Total_applicants = 0` foram mantidas e sinalizadas na coluna `Aplicações Confiáveis`, pois não é possível confirmar se o zero é real ou dado não coletado.

- Os 392 cargos distintos de `Designation` foram agrupados em categorias por palavra-chave, na coluna `Cargo Agrupado`. Os critérios estão na aba `Categorias` (a primeira palavra encontrada, em ordem de prioridade, define a categoria).



## Limitações e inconsistências conhecidas (temporárias)



- **Agrupamento de cargos incompleto:** 69 das 811 vagas (cerca de 8,5%) ficaram na categoria "Outros" por não conterem nenhuma palavra-chave da tabela. O refinamento da lista está pendente.

- **Zeros ambíguos em `Total\_applicants`:** 4 empresas (Wipro, ACURA, LTIMindtree e IDESLABS) concentram todos os zeros (16% a 25% das suas vagas), enquanto 6 empresas não têm nenhum. Esse padrão sugere possível diferença na coleta, e a causa não foi confirmada.

- **Sem dimensão temporal:** o dataset não tem data de publicação, então a análise mostra um retrato do momento, não evolução ao longo do tempo.

- **Palavras-chave genéricas:** termos como `data` também capturam "database", e a ordem da tabela de critérios influencia o resultado (por exemplo, "Test Engineer" cai em Engenharia, não em Testes/QA).



## Estrutura do repositório



- `data/raw/`: dado original, sem alterações

- `data/processed/`: planilha tratada

- `docs/`: documentação da análise



## Status



Em andamento: tratamento praticamente concluído, com pendências listadas acima; análise exploratória em desenvolvimento.

