# Produtos Alimentícios 🍞🥤

## Descrição do Projeto
Este projeto analisa **logs de eventos de usuários** relacionados a produtos alimentícios em uma plataforma digital.  
O objetivo é compreender o comportamento dos usuários, avaliar a qualidade dos dados, identificar eventos principais e verificar transições comuns entre eventos — além de realizar análises de grupos experimentais (A/B tests).

## Ferramentas e Bibliotecas Utilizadas
- **Pandas** – manipulação e análise de dados  
- **NumPy** – cálculos estatísticos  
- **Matplotlib** – visualizações gráficas  
- **Collections (Counter)** – contagem de transições de eventos  
- **Statsmodels** – testes estatísticos (proportions z-test)  

## Tabela
O dataset `logs_exp_us.csv` contém:
- **event_name** – nome do evento realizado pelo usuário  
- **user_id** – identificador único do usuário  
- **timestamp** – data e hora do evento  
- **experiment_group** – grupo experimental ao qual o usuário pertence (para A/B testing)  

## Metodologia
1. **Carregamento dos dados** e ajuste das colunas  
2. Conversão de datas (`timestamp`) e criação de colunas auxiliares  
3. Identificação de valores ausentes e limpeza de inconsistências  
4. Análise exploratória:  
   - Total de eventos e usuários únicos  
   - Eventos médios por usuário  
   - Distribuição de eventos ao longo do tempo  
5. Filtragem de dados confiáveis (eliminação de períodos iniciais pouco consistentes)  
6. Estudo da frequência de eventos e participação dos usuários  
7. Construção de **cadeias de eventos (transições mais comuns)**  
8. Identificação de **eventos isolados** (não conectados a outros)  
9. Aplicação de testes estatísticos em grupos experimentais  

## Pré-processamento
- Conversão de colunas (`timestamp`, `event_name`, `user_id`, `experiment_group`) para tipos adequados  
- Criação de colunas auxiliares (`date`, `datetime`)  
- Remoção de registros iniciais com baixa confiabilidade de dados  
- Segmentação por **grupos de experimento**  

## Análise dos Dados
- O volume de eventos cresce rapidamente após o início do período analisado, estabilizando em milhares de registros por dia  
- O número médio de eventos por usuário é elevado, indicando engajamento ativo  
- Alguns eventos concentram grande parte das interações, enquanto outros são pouco utilizados  
- Transições mais comuns revelam o **fluxo natural de navegação do usuário**  
- Foram encontrados **eventos isolados**, sem ligação clara com o restante do fluxo  

## Resultados
- Dados antes de **27/07** foram descartados por baixa confiabilidade  
- Após filtragem, obteve-se um conjunto de dados representativo e consistente  
- O comportamento dos usuários segue padrões claros de navegação entre eventos  
- A análise de grupos experimentais permite comparar diferenças entre **variantes de produto ou interface**  

## Aprendizados
- É essencial **filtrar datas confiáveis** antes de realizar análises de comportamento  
- A análise de transições de eventos ajuda a compreender o **funil do usuário**  
- Eventos isolados podem indicar funcionalidades pouco usadas ou problemas na coleta de dados  
- O uso de testes estatísticos fornece base para decisões em **experimentos A/B**  
- O comportamento do usuário pode ser usado para **otimizar produtos alimentícios digitais** (ex.: aplicativos de delivery, e-commerce de alimentos)
