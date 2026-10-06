# Viés Sistêmico em Vistos de Trabalho no Brasil: uma Análise com Regressão Logística e Estatística Inferencial

> Análise estatística (R/Shiny) de viés sistêmico em vistos de trabalho no Brasil, usando regressão logística sobre dados públicos de imigração.

## Etapa 1 - Problema central, mapeamento e hipóteses

### Problema de pesquisa

Este é um trabalho acadêmico que busca evidências de viés sistêmico contra continentes, países ou sub-regiões, através de análise inferencial com regressão logística, sobre dados públicos de concessão de vistos de trabalho no Brasil, de 2024 a setembro de 2025.

**Pergunta:** Controlando por Escolaridade, Norma Jurídica, Idade e Sexo, a chance de deferimento varia conforme o país, o continente ou a sub-região de origem?

### Mapeamento das variáveis

Para efeitos deste trabalho, serão excluídos os status intermediários ou burocráticos, focando apenas no deferimento ou não das solicitações.

#### Variável dependente

Y é o resultado da solicitação: 1 = Deferimento; 0 = Indeferimento.

#### Variável de interesse

$X_1$ é a origem do aplicante, em três níveis de granularidade, cada um em um modelo separado:

1. Continente
2. Sub-região (M49 – ONU)
3. País

*Categoria de referência:* Europa (a definir para sub-região e país).

#### Variáveis de controle

$X_2$ - Escolaridade
$X_3$ - Norma Jurídica
$X_6$ - Idade
$X_7$ - Sexo

*Opcionais (sensibilidade / Modelo C):*
$X_4$ - IDH da origem
$X_5$ - IDH-M do destino

### Modelos

- **Modelo A:** Y ~ $X_1$
- **Modelo B:** Y ~ $X_1$ + $X_2$ + $X_3$ + $X_6$ + $X_7$

### Hipótese

$H_0$: Após os controles, a chance de deferimento não muda por conta da origem (OR = 1); desvios são variância natural dos dados.

$H_1$: Se houver divergência significativa na chance de deferimento devido à origem, isso indica disparidade não explicada pelas variáveis observadas.

**Regra de decisão (fixada antes de rodar os modelos):** rejeitar $H_0$ se o IC 95% do OR de uma origem excluir 1, com correção de Holm para comparações múltiplas. Erros-padrão agrupados por país nos níveis continente e sub-região.

### Limitações

Disparidade não prova intenção. Variáveis não observadas (documentação, empregador, ocupação) podem explicar parte do resultado. A exclusão de "Em exigência" e "Cancelado" pode introduzir viés de seleção. A inclusão de renovações também pode introduzir viés de seleção, pois exige aprovação anterior; a análise principal considera pedidos iniciais, se a base permitir separá-los.

### Governança

Os dados pessoais dos aplicantes já estão anônimos em conformidade com a LGPD e a LAI.

Este é um trabalho acadêmico, independente e autoral, sem vínculo formal com o OBMigra ou com o órgão que publicizou a fonte dos dados.

## Etapa 2 - Compreensão dos Dados e Análise Exploratória (EDA)
> Em desenvolvimento

## Etapa 3 - Preparação dos Dados e Engenharia de Recursos
> Em desenvolvimento

## Etapa 4 - Modelagem Estatística
> Em desenvolvimento

## Etapa 5 - Avaliação e Validação

Métricas de validação:

- AIC / BIC (para comparação de modelos)
- Pseudo-R² (McFadden)
- Matriz de Resíduos / Teste de Hosmer-Lemeshow (ajuste do modelo), acompanhado de gráfico de calibração e AUC, pois o teste tende a rejeitar o ajuste em amostras grandes

> Em desenvolvimento

## Etapa 6 - Comunicação dos Resultados e Conclusões
> Em desenvolvimento

## Autor

pazoliveira
