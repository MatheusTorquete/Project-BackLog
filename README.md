## Análise e Visualização de Dados no Power BI: Projeto Backlog

Neste projeto, fui desafiado a analisar e visualizar dados relacionados ao Backlog de melhorias de processos em uma organização. O objetivo era entender e apresentar informações significativas a partir dos dados fornecidos. Abaixo estão os detalhes das etapas realizadas e das análises feitas.

### 1. **Verificação dos Dados**

Iniciei importando os dados do arquivo Excel para o Power BI. Garanti que os dados estavam corretos e que não havia valores nulos. Fiz uma revisão cuidadosa das colunas para entender o tipo de dados em cada uma.

### 2. **Total de Melhorias Solicitadas**

Criei uma medida chamada "Total de Melhorias Solicitadas" para contar o número total de melhorias solicitadas:

```DAX
Total de Melhorias Solicitadas = COUNTROWS(Backlog)
```

### 3. **Melhorias por Empresa**

Desenvolvi uma tabela dinâmica usando a seguinte medida DAX para contar o número de melhorias por empresa:

```DAX
Melhorias por Empresa = SUMMARIZE(Backlog, Backlog[Empresa], "Número de Melhorias", COUNTROWS(Backlog))
```

### 4. **Melhorias em Andamento e Não Iniciadas**

Calculei as melhorias em andamento e não iniciadas com as medidas:

```DAX
Melhorias em Andamento = CALCULATE(COUNTROWS(Backlog), Backlog[Status] = "Em Andamento")
Melhorias Não Iniciadas = CALCULATE(COUNTROWS(Backlog), Backlog[Status] = "Não Iniciado")
```

### 5. **Melhorias por Área**

Criei uma tabela para mostrar o número de melhorias por área:

```DAX
Melhorias por Área = SUMMARIZE(Backlog, Backlog[Área], "Número de Melhorias", COUNTROWS(Backlog))
```

### 6. **Melhorias por Status**

Visualizei as melhorias por status usando um gráfico de barras empilhadas com "Status" no eixo x e "Número de Melhorias" na altura das barras.

### 7. **Melhorias por Tipo de Ganho**

Desenvolvi uma tabela para mostrar o número de melhorias por tipo de ganho:

```DAX
Melhorias por Tipo de Ganho = SUMMARIZE(Backlog, Backlog[Tipo de ganho], "Número de Melhorias", COUNTROWS(Backlog))
```

### 8. **Dashboard Interativo**
![image](https://github.com/MatheusTorquete/Project-BackLog/assets/94683422/5e6cdac8-2b25-45a3-ad6c-28ba8a22bd41)


Integrei todas as visualizações e medidas criadas em um dashboard interativo no Power BI. 
Adicionei filtros para permitir uma análise mais detalhada por Empresa, Área, Status e Tipo de Ganho.



