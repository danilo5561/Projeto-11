# Análise do Funil de Vendas e Teste A/A/B para Aplicativo de Produtos Alimentícios

## Descrição do Projeto
Este projeto analisa o comportamento dos usuários de um aplicativo de produtos alimentícios. O objetivo é estudar o funil de vendas e avaliar os resultados de um teste A/A/B para decidir se a alteração nas fontes do aplicativo impacta significativamente a experiência do usuário.

### Objetivos:
1. **Funil de Vendas**:
   - Descobrir como os usuários avançam nas etapas do funil de vendas.
   - Identificar pontos de atrito em que os usuários abandonam o processo.
2. **Teste A/A/B**:
   - Avaliar se a nova fonte impacta os resultados.
   - Verificar a consistência dos dois grupos de controle (A/A).
   - Comparar o grupo de teste (B) com os grupos de controle para identificar diferenças significativas.

## Descrição dos Dados
Os dados utilizados estão no arquivo `/datasets/logs_exp_us.csv`. Cada linha representa um evento realizado por um usuário no aplicativo.

### Colunas:
- **EventName**: Nome do evento.
- **DeviceIDHash**: Identificador único do usuário.
- **EventTimestamp**: Hora do evento.
- **ExpId**: Número do experimento:
  - 246 e 247: Grupos de controle (A/A).
  - 248: Grupo de teste (B).

### Período:
Os dados foram analisados em um intervalo representativo, excluindo dados iniciais incompletos para garantir a confiabilidade.

## Metodologia
### 1. **Preparação dos Dados**:
- Renomeação de colunas.
- Tratamento de valores ausentes e ajuste de tipos de dados.
- Criação de colunas de data e hora.

### 2. **Análise do Funil de Vendas**:
- Identificação de eventos e suas frequências.
- Cálculo da proporção de usuários que executaram cada evento.
- Análise do funil, avaliando a perda de usuários em cada etapa.

### 3. **Teste A/A/B**:
- Verificação da semelhança entre os grupos de controle (246 e 247).
- Comparação entre os grupos de controle e o grupo de teste (248) para cada evento.
- Aplicação de testes estatísticos com níveis de significância de 0,05 e 0,1.

## Resultados do Experimento
### Funil de Vendas:
- Identificou-se que a maior perda de usuários ocorre na etapa **[OffersScreenAppear]**.
- Apenas uma proporção dos usuários completa o funil, desde o primeiro evento até o pagamento (conferir gráfico).

### Teste A/A/B:
1. **Grupos de Controle (A/A)**:
   - Os grupos de controle (246 e 247) foram confirmados como similares, com diferenças estatisticamente insignificantes na maioria dos eventos.

2. **Grupo de Teste (B)**:
   - No evento *OffersScreenAppear*, não houve diferença significativa entre os grupos.
   - Para os demais eventos, foram identificadas diferenças significativas na quantidade de usuários entre o grupo de teste (B) e os grupos de controle, especialmente ao utilizar um nível de significância de 0,1.
   - Com um limiar mais conservador (0,05), algumas diferenças deixaram de ser significativas.

### Conclusão:
O teste A/A confirmou a consistência dos grupos de controle. No entanto, o grupo de teste apresentou diferenças significativas em quase todos os eventos, especialmente com um limiar de 0,1. Isso sugere que a nova fonte pode impactar a experiência dos usuários. Por precaução, recomenda-se uma análise mais aprofundada antes de adotar as alterações de design.

#### Autor
[Danilo José](https://www.linkedin.com/in/danilojosedelara/)
Projeto desenvolvido como parte do curso de análise de dados.