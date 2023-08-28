## Exercício 1: Vestibular

Considere que a os dados gerados na célula abaixo contêm o número de acertos de 100 alunos em um vestibular para um curso de exatas, divididas pelos respectivos assuntos. Considere que cada assunto possui um número de questões conforme a tabela abaixo:

| assunto | número de questões |
|:---:|:---:|
| Matemática | 24 |
| Português | 18 |
| Geografia | 8 |
| Inglês | 8 |
| História | 8 |
| Física | 12 |
| Química | 12 |

Usando os comandos de operações com DataFrames que você aprendeu na Aula 03, calcule:

1. (operações com escalar) Calcule o percentual de acerto dos alunos por assunto.  
2. (operações entre *DataFrames) Calcule o total de acertos de cada aluno.  
3. Calcule o porcentual geral de cada aluno.  
4. Suponha que a nota de corte para a segunda fase seja 45. Quantos alunos tiveram nota maior que 45?  


```python
import pandas as pd
import numpy as np

np.random.seed(42)
df_mat = pd.DataFrame(np.random.randint(24, size=(100, 1)), columns=['Qt_acertos_mat'])

df_por = pd.DataFrame(np.random.randint(18, size=(100, 1)), columns=['Qt_acertos_por'])

df_geo = pd.DataFrame(np.random.randint(8, size=(100, 1)), columns=['Qt_acertos_geo'])

df_ing = pd.DataFrame(np.random.randint(8, size=(100, 1)), columns=['Qt_acertos_ing'])

df_his = pd.DataFrame(np.random.randint(8, size=(100, 1)), columns=['Qt_acertos_his'])

df_fis = pd.DataFrame(np.random.randint(12, size=(100, 1)), columns=['Qt_acertos_fis'])

df_qui = pd.DataFrame(np.random.randint(12, size=(100, 1)), columns=['Qt_acertos_qui'])
```


```python
# 1) Seu código aqui

df_mat['numero_questoes_mat'] = 24
df_mat['percentual_acertos_mat'] = df_mat['Qt_acertos_mat'] / df_mat['numero_questoes_mat']

df_por['numero_questoes_por'] = 18
df_por['percentual_acertos_por'] = df_por['Qt_acertos_por'] / df_por['numero_questoes_por']

df_geo['numero_questoes_geo'] = 8
df_geo['percentual_acertos_geo'] = df_geo['Qt_acertos_geo'] / df_geo['numero_questoes_geo']

df_ing['numero_questoes_ing'] = 8
df_ing['percentual_acertos_ing'] = df_ing['Qt_acertos_ing'] / df_ing['numero_questoes_ing']

df_his['numero_questoes_his'] = 8
df_his['percentual_acertos_his'] = df_his['Qt_acertos_his'] / df_his['numero_questoes_his']

df_fis['numero_questoes_fis'] = 12
df_fis['percentual_acertos_fis'] = df_fis['Qt_acertos_fis'] / df_fis['numero_questoes_fis']

df_qui['numero_questoes_qui'] = 12
df_qui['percentual_acertos_qui'] = df_qui['Qt_acertos_qui'] / df_qui['numero_questoes_qui']

```


```python
df = pd.concat([df_mat, df_por, df_geo, df_ing, df_his, df_fis, df_qui], axis=1)
df.index += 1
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Qt_acertos_mat</th>
      <th>numero_questoes_mat</th>
      <th>percentual_acertos_mat</th>
      <th>Qt_acertos_por</th>
      <th>numero_questoes_por</th>
      <th>percentual_acertos_por</th>
      <th>Qt_acertos_geo</th>
      <th>numero_questoes_geo</th>
      <th>percentual_acertos_geo</th>
      <th>Qt_acertos_ing</th>
      <th>...</th>
      <th>percentual_acertos_ing</th>
      <th>Qt_acertos_his</th>
      <th>numero_questoes_his</th>
      <th>percentual_acertos_his</th>
      <th>Qt_acertos_fis</th>
      <th>numero_questoes_fis</th>
      <th>percentual_acertos_fis</th>
      <th>Qt_acertos_qui</th>
      <th>numero_questoes_qui</th>
      <th>percentual_acertos_qui</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>6</td>
      <td>24</td>
      <td>0.250000</td>
      <td>7</td>
      <td>18</td>
      <td>0.388889</td>
      <td>7</td>
      <td>8</td>
      <td>0.875</td>
      <td>3</td>
      <td>...</td>
      <td>0.375</td>
      <td>1</td>
      <td>8</td>
      <td>0.125</td>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>24</td>
      <td>0.791667</td>
      <td>10</td>
      <td>18</td>
      <td>0.555556</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>0</td>
      <td>...</td>
      <td>0.000</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>11</td>
      <td>12</td>
      <td>0.916667</td>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
    </tr>
    <tr>
      <th>3</th>
      <td>14</td>
      <td>24</td>
      <td>0.583333</td>
      <td>16</td>
      <td>18</td>
      <td>0.888889</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>5</td>
      <td>...</td>
      <td>0.625</td>
      <td>7</td>
      <td>8</td>
      <td>0.875</td>
      <td>4</td>
      <td>12</td>
      <td>0.333333</td>
      <td>4</td>
      <td>12</td>
      <td>0.333333</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10</td>
      <td>24</td>
      <td>0.416667</td>
      <td>7</td>
      <td>18</td>
      <td>0.388889</td>
      <td>3</td>
      <td>8</td>
      <td>0.375</td>
      <td>4</td>
      <td>...</td>
      <td>0.500</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7</td>
      <td>24</td>
      <td>0.291667</td>
      <td>2</td>
      <td>18</td>
      <td>0.111111</td>
      <td>2</td>
      <td>8</td>
      <td>0.250</td>
      <td>7</td>
      <td>...</td>
      <td>0.875</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>9</td>
      <td>12</td>
      <td>0.750000</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>96</th>
      <td>6</td>
      <td>24</td>
      <td>0.250000</td>
      <td>4</td>
      <td>18</td>
      <td>0.222222</td>
      <td>7</td>
      <td>8</td>
      <td>0.875</td>
      <td>1</td>
      <td>...</td>
      <td>0.125</td>
      <td>4</td>
      <td>8</td>
      <td>0.500</td>
      <td>9</td>
      <td>12</td>
      <td>0.750000</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
    </tr>
    <tr>
      <th>97</th>
      <td>8</td>
      <td>24</td>
      <td>0.333333</td>
      <td>1</td>
      <td>18</td>
      <td>0.055556</td>
      <td>4</td>
      <td>8</td>
      <td>0.500</td>
      <td>6</td>
      <td>...</td>
      <td>0.750</td>
      <td>1</td>
      <td>8</td>
      <td>0.125</td>
      <td>4</td>
      <td>12</td>
      <td>0.333333</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
    </tr>
    <tr>
      <th>98</th>
      <td>23</td>
      <td>24</td>
      <td>0.958333</td>
      <td>5</td>
      <td>18</td>
      <td>0.277778</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>2</td>
      <td>...</td>
      <td>0.250</td>
      <td>4</td>
      <td>8</td>
      <td>0.500</td>
      <td>1</td>
      <td>12</td>
      <td>0.083333</td>
      <td>5</td>
      <td>12</td>
      <td>0.416667</td>
    </tr>
    <tr>
      <th>99</th>
      <td>0</td>
      <td>24</td>
      <td>0.000000</td>
      <td>10</td>
      <td>18</td>
      <td>0.555556</td>
      <td>3</td>
      <td>8</td>
      <td>0.375</td>
      <td>1</td>
      <td>...</td>
      <td>0.125</td>
      <td>5</td>
      <td>8</td>
      <td>0.625</td>
      <td>10</td>
      <td>12</td>
      <td>0.833333</td>
      <td>11</td>
      <td>12</td>
      <td>0.916667</td>
    </tr>
    <tr>
      <th>100</th>
      <td>11</td>
      <td>24</td>
      <td>0.458333</td>
      <td>15</td>
      <td>18</td>
      <td>0.833333</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>1</td>
      <td>...</td>
      <td>0.125</td>
      <td>6</td>
      <td>8</td>
      <td>0.750</td>
      <td>7</td>
      <td>12</td>
      <td>0.583333</td>
      <td>2</td>
      <td>12</td>
      <td>0.166667</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 21 columns</p>
</div>




```python
# 2) Seu código aqui
df['qtd_acertos_total'] = df[['Qt_acertos_mat', 'Qt_acertos_por', 'Qt_acertos_geo', 'Qt_acertos_ing', 'Qt_acertos_his', 'Qt_acertos_fis', 'Qt_acertos_qui']].sum(axis=1) 
df['qtd_acertos_total'].to_frame()                              
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>qtd_acertos_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>35</td>
    </tr>
    <tr>
      <th>2</th>
      <td>48</td>
    </tr>
    <tr>
      <th>3</th>
      <td>50</td>
    </tr>
    <tr>
      <th>4</th>
      <td>32</td>
    </tr>
    <tr>
      <th>5</th>
      <td>30</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>96</th>
      <td>34</td>
    </tr>
    <tr>
      <th>97</th>
      <td>27</td>
    </tr>
    <tr>
      <th>98</th>
      <td>40</td>
    </tr>
    <tr>
      <th>99</th>
      <td>40</td>
    </tr>
    <tr>
      <th>100</th>
      <td>42</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 1 columns</p>
</div>




```python
# 3) Seu código aqui
df['qtd_questoes_total'] = df[['numero_questoes_mat', 'numero_questoes_por', 'numero_questoes_geo', 'numero_questoes_ing', 'numero_questoes_his', 'numero_questoes_fis', 'numero_questoes_qui']].sum(axis=1)
df['percentual_geral'] = df['qtd_acertos_total'] / df['qtd_questoes_total']
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Qt_acertos_mat</th>
      <th>numero_questoes_mat</th>
      <th>percentual_acertos_mat</th>
      <th>Qt_acertos_por</th>
      <th>numero_questoes_por</th>
      <th>percentual_acertos_por</th>
      <th>Qt_acertos_geo</th>
      <th>numero_questoes_geo</th>
      <th>percentual_acertos_geo</th>
      <th>Qt_acertos_ing</th>
      <th>...</th>
      <th>percentual_acertos_his</th>
      <th>Qt_acertos_fis</th>
      <th>numero_questoes_fis</th>
      <th>percentual_acertos_fis</th>
      <th>Qt_acertos_qui</th>
      <th>numero_questoes_qui</th>
      <th>percentual_acertos_qui</th>
      <th>qtd_acertos_total</th>
      <th>qtd_questoes_total</th>
      <th>percentual_geral</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>6</td>
      <td>24</td>
      <td>0.250000</td>
      <td>7</td>
      <td>18</td>
      <td>0.388889</td>
      <td>7</td>
      <td>8</td>
      <td>0.875</td>
      <td>3</td>
      <td>...</td>
      <td>0.125</td>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
      <td>35</td>
      <td>90</td>
      <td>0.388889</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>24</td>
      <td>0.791667</td>
      <td>10</td>
      <td>18</td>
      <td>0.555556</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>0</td>
      <td>...</td>
      <td>0.000</td>
      <td>11</td>
      <td>12</td>
      <td>0.916667</td>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
      <td>48</td>
      <td>90</td>
      <td>0.533333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>14</td>
      <td>24</td>
      <td>0.583333</td>
      <td>16</td>
      <td>18</td>
      <td>0.888889</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>5</td>
      <td>...</td>
      <td>0.875</td>
      <td>4</td>
      <td>12</td>
      <td>0.333333</td>
      <td>4</td>
      <td>12</td>
      <td>0.333333</td>
      <td>50</td>
      <td>90</td>
      <td>0.555556</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10</td>
      <td>24</td>
      <td>0.416667</td>
      <td>7</td>
      <td>18</td>
      <td>0.388889</td>
      <td>3</td>
      <td>8</td>
      <td>0.375</td>
      <td>4</td>
      <td>...</td>
      <td>0.000</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
      <td>32</td>
      <td>90</td>
      <td>0.355556</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7</td>
      <td>24</td>
      <td>0.291667</td>
      <td>2</td>
      <td>18</td>
      <td>0.111111</td>
      <td>2</td>
      <td>8</td>
      <td>0.250</td>
      <td>7</td>
      <td>...</td>
      <td>0.000</td>
      <td>9</td>
      <td>12</td>
      <td>0.750000</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
      <td>30</td>
      <td>90</td>
      <td>0.333333</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>96</th>
      <td>6</td>
      <td>24</td>
      <td>0.250000</td>
      <td>4</td>
      <td>18</td>
      <td>0.222222</td>
      <td>7</td>
      <td>8</td>
      <td>0.875</td>
      <td>1</td>
      <td>...</td>
      <td>0.500</td>
      <td>9</td>
      <td>12</td>
      <td>0.750000</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
      <td>34</td>
      <td>90</td>
      <td>0.377778</td>
    </tr>
    <tr>
      <th>97</th>
      <td>8</td>
      <td>24</td>
      <td>0.333333</td>
      <td>1</td>
      <td>18</td>
      <td>0.055556</td>
      <td>4</td>
      <td>8</td>
      <td>0.500</td>
      <td>6</td>
      <td>...</td>
      <td>0.125</td>
      <td>4</td>
      <td>12</td>
      <td>0.333333</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
      <td>27</td>
      <td>90</td>
      <td>0.300000</td>
    </tr>
    <tr>
      <th>98</th>
      <td>23</td>
      <td>24</td>
      <td>0.958333</td>
      <td>5</td>
      <td>18</td>
      <td>0.277778</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>2</td>
      <td>...</td>
      <td>0.500</td>
      <td>1</td>
      <td>12</td>
      <td>0.083333</td>
      <td>5</td>
      <td>12</td>
      <td>0.416667</td>
      <td>40</td>
      <td>90</td>
      <td>0.444444</td>
    </tr>
    <tr>
      <th>99</th>
      <td>0</td>
      <td>24</td>
      <td>0.000000</td>
      <td>10</td>
      <td>18</td>
      <td>0.555556</td>
      <td>3</td>
      <td>8</td>
      <td>0.375</td>
      <td>1</td>
      <td>...</td>
      <td>0.625</td>
      <td>10</td>
      <td>12</td>
      <td>0.833333</td>
      <td>11</td>
      <td>12</td>
      <td>0.916667</td>
      <td>40</td>
      <td>90</td>
      <td>0.444444</td>
    </tr>
    <tr>
      <th>100</th>
      <td>11</td>
      <td>24</td>
      <td>0.458333</td>
      <td>15</td>
      <td>18</td>
      <td>0.833333</td>
      <td>0</td>
      <td>8</td>
      <td>0.000</td>
      <td>1</td>
      <td>...</td>
      <td>0.750</td>
      <td>7</td>
      <td>12</td>
      <td>0.583333</td>
      <td>2</td>
      <td>12</td>
      <td>0.166667</td>
      <td>42</td>
      <td>90</td>
      <td>0.466667</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 24 columns</p>
</div>




```python
# 4) Seu código aqui
segunda_fase = df[df['qtd_acertos_total'] > 45]

print('Quantidade de alunos com nota maior que 45:')
print(segunda_fase.shape[0])
```

    Quantidade de alunos com nota maior que 45:
    31
    

## 2) Vestibular II

Ainda sobre o mesmo banco de dados:

1. Neste vestibular, quem 'zera' em matemática, física ou química está desqualificado. Monte um novo *DataFrame* com os alunos desqualificados por este critério.
2. Quantos são esses alunos?
3. Qual a média desses alunos em história e geografia?
4. Monte um *DataFrame* com os alunos que passaram para a segunda fase. Repare que estes alunos não podem ter sido desqualificados.


```python
# seu código aqui
df_eliminados = df[(df['Qt_acertos_mat'] == 0) | 
                   (df['Qt_acertos_fis'] == 0) | 
                   (df['Qt_acertos_qui'] == 0)]

df_eliminados[['Qt_acertos_mat', 'Qt_acertos_fis', 'Qt_acertos_qui']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Qt_acertos_mat</th>
      <th>Qt_acertos_fis</th>
      <th>Qt_acertos_qui</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>10</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>11</th>
      <td>10</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>20</td>
      <td>0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>15</th>
      <td>7</td>
      <td>4</td>
      <td>0</td>
    </tr>
    <tr>
      <th>21</th>
      <td>23</td>
      <td>2</td>
      <td>0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>0</td>
      <td>4</td>
      <td>8</td>
    </tr>
    <tr>
      <th>27</th>
      <td>11</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>28</th>
      <td>21</td>
      <td>3</td>
      <td>0</td>
    </tr>
    <tr>
      <th>34</th>
      <td>14</td>
      <td>6</td>
      <td>0</td>
    </tr>
    <tr>
      <th>36</th>
      <td>11</td>
      <td>0</td>
      <td>11</td>
    </tr>
    <tr>
      <th>50</th>
      <td>8</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>57</th>
      <td>7</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>66</th>
      <td>1</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>67</th>
      <td>5</td>
      <td>0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>73</th>
      <td>11</td>
      <td>0</td>
      <td>9</td>
    </tr>
    <tr>
      <th>74</th>
      <td>1</td>
      <td>0</td>
      <td>11</td>
    </tr>
    <tr>
      <th>75</th>
      <td>9</td>
      <td>7</td>
      <td>0</td>
    </tr>
    <tr>
      <th>85</th>
      <td>15</td>
      <td>0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>90</th>
      <td>23</td>
      <td>9</td>
      <td>0</td>
    </tr>
    <tr>
      <th>93</th>
      <td>14</td>
      <td>8</td>
      <td>0</td>
    </tr>
    <tr>
      <th>95</th>
      <td>0</td>
      <td>3</td>
      <td>8</td>
    </tr>
    <tr>
      <th>99</th>
      <td>0</td>
      <td>10</td>
      <td>11</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Quantos são esses alunos?
print(f'Alunos eliminados: {df_eliminados.shape[0]}.')
```

    Alunos eliminados: 23.
    


```python
# Qual a média desses alunos em história e geografia?

media_eliminado_his = round(df_eliminados['Qt_acertos_his'].mean(), 2)
media_eliminado_geo = round(df_eliminados['Qt_acertos_geo'].mean(), 2)

print('Média dos alunos eliminados nas questões de história: {}.'.format(media_eliminado_his))
print('Média dos alunos eliminados nas questões de geografia: {}.'.format(media_eliminado_geo))
```

    Média dos alunos eliminados nas questões de história: 3.43.
    Média dos alunos eliminados nas questões de geografia: 3.22.
    


```python
# Monte um DataFrame com os alunos que passaram para a segunda fase. Repare que estes alunos não podem ter sido desqualificados.

alunos_seguda_fase = pd.merge(left=segunda_fase, right=df_eliminados, how='inner')
alunos_seguda_fase
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Qt_acertos_mat</th>
      <th>numero_questoes_mat</th>
      <th>percentual_acertos_mat</th>
      <th>Qt_acertos_por</th>
      <th>numero_questoes_por</th>
      <th>percentual_acertos_por</th>
      <th>Qt_acertos_geo</th>
      <th>numero_questoes_geo</th>
      <th>percentual_acertos_geo</th>
      <th>Qt_acertos_ing</th>
      <th>...</th>
      <th>percentual_acertos_his</th>
      <th>Qt_acertos_fis</th>
      <th>numero_questoes_fis</th>
      <th>percentual_acertos_fis</th>
      <th>Qt_acertos_qui</th>
      <th>numero_questoes_qui</th>
      <th>percentual_acertos_qui</th>
      <th>qtd_acertos_total</th>
      <th>qtd_questoes_total</th>
      <th>percentual_geral</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>23</td>
      <td>24</td>
      <td>0.958333</td>
      <td>11</td>
      <td>18</td>
      <td>0.611111</td>
      <td>6</td>
      <td>8</td>
      <td>0.750</td>
      <td>5</td>
      <td>...</td>
      <td>0.750</td>
      <td>2</td>
      <td>12</td>
      <td>0.166667</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>53</td>
      <td>90</td>
      <td>0.588889</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>24</td>
      <td>0.875000</td>
      <td>13</td>
      <td>18</td>
      <td>0.722222</td>
      <td>1</td>
      <td>8</td>
      <td>0.125</td>
      <td>5</td>
      <td>...</td>
      <td>0.875</td>
      <td>3</td>
      <td>12</td>
      <td>0.250000</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>50</td>
      <td>90</td>
      <td>0.555556</td>
    </tr>
    <tr>
      <th>2</th>
      <td>11</td>
      <td>24</td>
      <td>0.458333</td>
      <td>14</td>
      <td>18</td>
      <td>0.777778</td>
      <td>6</td>
      <td>8</td>
      <td>0.750</td>
      <td>3</td>
      <td>...</td>
      <td>0.375</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>11</td>
      <td>12</td>
      <td>0.916667</td>
      <td>48</td>
      <td>90</td>
      <td>0.533333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>11</td>
      <td>24</td>
      <td>0.458333</td>
      <td>16</td>
      <td>18</td>
      <td>0.888889</td>
      <td>3</td>
      <td>8</td>
      <td>0.375</td>
      <td>4</td>
      <td>...</td>
      <td>0.875</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>9</td>
      <td>12</td>
      <td>0.750000</td>
      <td>50</td>
      <td>90</td>
      <td>0.555556</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>24</td>
      <td>0.958333</td>
      <td>11</td>
      <td>18</td>
      <td>0.611111</td>
      <td>7</td>
      <td>8</td>
      <td>0.875</td>
      <td>7</td>
      <td>...</td>
      <td>0.750</td>
      <td>9</td>
      <td>12</td>
      <td>0.750000</td>
      <td>0</td>
      <td>12</td>
      <td>0.000000</td>
      <td>63</td>
      <td>90</td>
      <td>0.700000</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 24 columns</p>
</div>



## 3) Vacinações no Acre
Vamos trabalhar agora com a base de vacinações no Acre. Para facilitar a sua vida, copiamos o link do arquivo na célula abaixo.

1. Quantas vacinas estão registradas nessa base?  
2. Quantos pacientes foram vacinados? (considere um paciente para cada valor único de ```paciente_id```)  
3. Quantos pacientes únicos tomaram a primeira dose? OBS: Há um caractere especial neste campo. Receba os valores do campo com o método ```.unique()```.   
4. Quantos pacientes com menos de 18 anos foram vacinados?  
5. Quantos estabelecimentos aplicaram vacina no Acre?


**OBS:** O portal do DATASUS pode apresentar instabilidades, retornando um erro na segunda célula abaixo. Por este motivo está disponível uma base estática, que se for baixada para o seu *working directory* pode ser lida com este comando: ```df = pd.read_csv('registros de vacinacao covid ACRE.csv', sep=';')```.

**OBS2:** Para saber qual é o seu working directory, rode no jupyter: ```!pwd```.


```python
arquivo = 'registros de vacinacao covid ACRE.csv'
```


```python
# 1) Sua solução aqui
df = pd.read_csv(arquivo, sep=';')

```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>document_id</th>
      <th>paciente_id</th>
      <th>paciente_idade</th>
      <th>paciente_datanascimento</th>
      <th>paciente_enumsexobiologico</th>
      <th>paciente_racacor_codigo</th>
      <th>paciente_racacor_valor</th>
      <th>paciente_endereco_coibgemunicipio</th>
      <th>paciente_endereco_copais</th>
      <th>paciente_endereco_nmmunicipio</th>
      <th>...</th>
      <th>vacina_lote</th>
      <th>vacina_fabricante_nome</th>
      <th>vacina_fabricante_referencia</th>
      <th>vacina_dataaplicacao</th>
      <th>vacina_descricao_dose</th>
      <th>vacina_codigo</th>
      <th>vacina_nome</th>
      <th>sistema_origem</th>
      <th>data_importacao_rnds</th>
      <th>id_sistema_origem</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>b19cd280-474c-4c22-a35d-8c06bc04a4e0-i0b0</td>
      <td>2e091c9a37d3f50d1d705fc80c6448c6fc69b44da9e936...</td>
      <td>69</td>
      <td>1951-12-28</td>
      <td>F</td>
      <td>3</td>
      <td>PARDA</td>
      <td>120050.0</td>
      <td>10.0</td>
      <td>SENA MADUREIRA</td>
      <td>...</td>
      <td>210052A</td>
      <td>FUNDACAO BUTANTAN</td>
      <td>Organization/61189445000156</td>
      <td>2021-03-23</td>
      <td>1ª Dose</td>
      <td>86</td>
      <td>Covid-19-Coronavac-Sinovac/Butantan</td>
      <td>Novo PNI</td>
      <td>2021-03-25T03:27:19.000Z</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>a1acc0b6-1cf6-4c4b-adcb-06b473a0faaf-i0b0</td>
      <td>f4e17a9e5354cb45e223d85eda02fb2f76048c801675f5...</td>
      <td>81</td>
      <td>1939-11-22</td>
      <td>M</td>
      <td>3</td>
      <td>PARDA</td>
      <td>120040.0</td>
      <td>10.0</td>
      <td>RIO BRANCO</td>
      <td>...</td>
      <td>210110</td>
      <td>FUNDACAO BUTANTAN</td>
      <td>Organization/61189445000156</td>
      <td>2021-04-29</td>
      <td>2ª Dose</td>
      <td>86</td>
      <td>Covid-19-Coronavac-Sinovac/Butantan</td>
      <td>Novo PNI</td>
      <td>2021-04-30T16:03:14.000Z</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>af279a98-ba1f-47ea-8214-314a98040b0d-i0b0</td>
      <td>6734b26bccf826130ebffa66575977bbe71477b12bcf42...</td>
      <td>69</td>
      <td>1951-08-14</td>
      <td>M</td>
      <td>4</td>
      <td>AMARELA</td>
      <td>120020.0</td>
      <td>10.0</td>
      <td>CRUZEIRO DO SUL</td>
      <td>...</td>
      <td>210135</td>
      <td>FUNDACAO BUTANTAN</td>
      <td>Organization/61189445000156</td>
      <td>2021-04-16</td>
      <td>1ª Dose</td>
      <td>86</td>
      <td>Covid-19-Coronavac-Sinovac/Butantan</td>
      <td>Novo PNI</td>
      <td>2021-04-16T15:54:39.000Z</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4879308e-5050-46bb-b8e2-11fa5646a05c-i0b0</td>
      <td>84a341fd350c1ba7117fccbb4d2df417bc0fac0fffac37...</td>
      <td>51</td>
      <td>1969-12-15</td>
      <td>F</td>
      <td>3</td>
      <td>PARDA</td>
      <td>120040.0</td>
      <td>10.0</td>
      <td>RIO BRANCO</td>
      <td>...</td>
      <td>202010040</td>
      <td>FUNDACAO BUTANTAN</td>
      <td>Organization/61189445000156</td>
      <td>2021-02-19</td>
      <td>2ª Dose</td>
      <td>86</td>
      <td>Covid-19-Coronavac-Sinovac/Butantan</td>
      <td>Novo PNI</td>
      <td>2021-03-10T14:40:54.000Z</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>000e911b-e3a4-4114-a735-d1f2e6e3797f-i0b0</td>
      <td>c59571e19f368d4b0cf08cd3bcabb32e5cd8baad5340f6...</td>
      <td>65</td>
      <td>1955-11-21</td>
      <td>M</td>
      <td>3</td>
      <td>PARDA</td>
      <td>120040.0</td>
      <td>10.0</td>
      <td>RIO BRANCO</td>
      <td>...</td>
      <td>212VCD001ZVB</td>
      <td>FUNDACAO OSWALDO CRUZ</td>
      <td>Organization/33781055000135</td>
      <td>2021-03-29</td>
      <td>1ª Dose</td>
      <td>85</td>
      <td>Vacina Covid-19 - Covishield</td>
      <td>Novo PNI</td>
      <td>2021-04-03T19:44:28.000Z</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 34 columns</p>
</div>




```python
# Quantas vacinas estão registradas nessa base?

print('Total de vacinas registrada em nossa BD:')
print(df.shape[0])
```

    Total de vacinas registrada em nossa BD:
    169071
    


```python
# 2) Quantos pacientes foram vacinados? (considere um paciente para cada valor único de paciente_id)
print('Total de pacientes vacinados:')
print(df['paciente_id'].nunique())
```

    Total de pacientes vacinados:
    120517
    


```python
# 3) Quantos pacientes únicos tomaram a primeira dose? OBS: Há um caractere especial neste campo. Receba os valores do campo com o método .unique().
primeira_dose = df['vacina_descricao_dose'].unique()[0]
pacientes_prim_dose = df[df['vacina_descricao_dose'] == primeira_dose]
total_pac_primeira_dose = pacientes_prim_dose['paciente_id'].nunique()

print('Total de pacientes que já tomaram a primeira dose:')
print(total_pac_primeira_dose)

```

    Total de pacientes que já tomaram a primeira dose:
    119713
    


```python
# 4) Quantos pacientes com menos de 18 anos foram vacinados?
df_menor = df[df["paciente_idade"]<18]
total_menor_18 = df_menor['paciente_id'].nunique()

print('Pacientes com menos de 18 anos que foram vacinados:')
print(total_menor_18)
```

    Pacientes com menos de 18 anos que foram vacinados:
    47
    


```python
# 5) Quantos estabelecimentos aplicaram vacina no Acre?

qtd_estab_aplicaram_vacina = df['estabelecimento_razaosocial'].nunique()
print('Total de estabelecimento que aplicaram vacina no ACRE:')
print(qtd_estab_aplicaram_vacina)

print("\n\033[1;31;47mDados dos estabelecimentos:\033[m")

df.loc[:,'estabelecimento_valor' : 'estabelecimento_uf']
```

    Total de estabelecimento que aplicaram vacina no ACRE:
    42
    
    [1;31;47mDados dos estabelecimentos:[m
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>estabelecimento_valor</th>
      <th>estabelecimento_razaosocial</th>
      <th>estalecimento_nofantasia</th>
      <th>estabelecimento_municipio_codigo</th>
      <th>estabelecimento_municipio_nome</th>
      <th>estabelecimento_uf</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3541592</td>
      <td>PREFEITURA MUNICIPAL DE SENA MADUREIRA</td>
      <td>UNIDADE BASICA DE SAUDE MARIA DAS DORES DE PAULA</td>
      <td>120050</td>
      <td>SENA MADUREIRA</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>1</th>
      <td>6917291</td>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
      <td>DEPARTAMENTO DE VIGILANCIA EPIDEMIOLOGICA E AM...</td>
      <td>120040</td>
      <td>RIO BRANCO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6159087</td>
      <td>PREFEITURA MUNICIPAL DE CRUZEIRO DO SUL</td>
      <td>SECRETARIA MUNICIPAL DE SAUDE DE CRUZEIRO DO SUL</td>
      <td>120020</td>
      <td>CRUZEIRO DO SUL</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6917291</td>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
      <td>DEPARTAMENTO DE VIGILANCIA EPIDEMIOLOGICA E AM...</td>
      <td>120040</td>
      <td>RIO BRANCO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6917291</td>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
      <td>DEPARTAMENTO DE VIGILANCIA EPIDEMIOLOGICA E AM...</td>
      <td>120040</td>
      <td>RIO BRANCO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>169066</th>
      <td>7625855</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
      <td>POLO BASE DE MARECHAL THAUMATURGO</td>
      <td>120035</td>
      <td>MARECHAL THAUMATURGO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>169067</th>
      <td>6917291</td>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
      <td>DEPARTAMENTO DE VIGILANCIA EPIDEMIOLOGICA E AM...</td>
      <td>120040</td>
      <td>RIO BRANCO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>169068</th>
      <td>2001039</td>
      <td>PREFEITURA MUNICIPAL DE CAPIXABA</td>
      <td>UNIDADE DE SAUDE DA FAMILIA DR LUIZ FERNANDO M...</td>
      <td>120017</td>
      <td>CAPIXABA</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>169069</th>
      <td>2002876</td>
      <td>SECRETARIA MUNCIPAL DE SAUDE</td>
      <td>CENTRO DE SAUDE RAIMUNDA PORFIRIO DE BRITO RAMOS</td>
      <td>120013</td>
      <td>BUJARI</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>169070</th>
      <td>6917291</td>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
      <td>DEPARTAMENTO DE VIGILANCIA EPIDEMIOLOGICA E AM...</td>
      <td>120040</td>
      <td>RIO BRANCO</td>
      <td>AC</td>
    </tr>
  </tbody>
</table>
<p>169071 rows × 6 columns</p>
</div>



## 4) Vacinação II
Gere um *DataFrame* que contenha somente os estabelecimentos que aplicaram vcinas a menores de 18 anos. Nesse *DataFrame* devem conter somente os dados dos estabelecimentos, mais uma coluna sendo a quantidade de vacinas que o estabelecimento aplicou a menores de 18 anos.  
  
1. crie uma cópia do *DataFrame* original, contendo somente os registros de vacinas realizadas a menores de 18 anos.  
2. crie uma lista das colunas desse *DataFrame* com o atributo de *DataFrame* **.columns()**  
3. Nesse *DataFrame* faça uma contagem do campo ```vacina_categoria_nome```.
3. a partir da lista de colunas, escolha somente aquelas que são referentes ao estabelecimento, faça uma lista com esses valores.  
4. usando o método *.loc*, selecione somente essas variáveis  
5. Aplique o método **.drop_duplicates** e crie uma lista com uma linha para cada estabelecimento, com os dados do estabelecimento  


```python
# 1) crie uma cópia do DataFrame original, contendo somente os registros de vacinas realizadas a menores de 18 anos
df_menor_18 = df[df["paciente_idade"]<18].copy()
df_menor_18.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 55 entries, 1567 to 164449
    Data columns (total 34 columns):
     #   Column                                    Non-Null Count  Dtype  
    ---  ------                                    --------------  -----  
     0   document_id                               55 non-null     object 
     1   paciente_id                               55 non-null     object 
     2   paciente_idade                            55 non-null     int64  
     3   paciente_datanascimento                   55 non-null     object 
     4   paciente_enumsexobiologico                55 non-null     object 
     5   paciente_racacor_codigo                   55 non-null     int64  
     6   paciente_racacor_valor                    55 non-null     object 
     7   paciente_endereco_coibgemunicipio         52 non-null     float64
     8   paciente_endereco_copais                  52 non-null     float64
     9   paciente_endereco_nmmunicipio             52 non-null     object 
     10  paciente_endereco_nmpais                  52 non-null     object 
     11  paciente_endereco_uf                      52 non-null     object 
     12  paciente_endereco_cep                     42 non-null     float64
     13  paciente_nacionalidade_enumnacionalidade  55 non-null     object 
     14  estabelecimento_valor                     55 non-null     int64  
     15  estabelecimento_razaosocial               55 non-null     object 
     16  estalecimento_nofantasia                  55 non-null     object 
     17  estabelecimento_municipio_codigo          55 non-null     int64  
     18  estabelecimento_municipio_nome            55 non-null     object 
     19  estabelecimento_uf                        55 non-null     object 
     20  vacina_grupoatendimento_codigo            55 non-null     int64  
     21  vacina_grupoatendimento_nome              54 non-null     object 
     22  vacina_categoria_codigo                   54 non-null     float64
     23  vacina_categoria_nome                     54 non-null     object 
     24  vacina_lote                               55 non-null     object 
     25  vacina_fabricante_nome                    55 non-null     object 
     26  vacina_fabricante_referencia              53 non-null     object 
     27  vacina_dataaplicacao                      55 non-null     object 
     28  vacina_descricao_dose                     55 non-null     object 
     29  vacina_codigo                             55 non-null     int64  
     30  vacina_nome                               55 non-null     object 
     31  sistema_origem                            55 non-null     object 
     32  data_importacao_rnds                      55 non-null     object 
     33  id_sistema_origem                         0 non-null      float64
    dtypes: float64(5), int64(6), object(23)
    memory usage: 15.0+ KB
    


```python
# 2) crie uma lista das colunas desse DataFrame com o atributo de DataFrame .columns()
df_menor.columns
```




    Index(['document_id', 'paciente_id', 'paciente_idade',
           'paciente_datanascimento', 'paciente_enumsexobiologico',
           'paciente_racacor_codigo', 'paciente_racacor_valor',
           'paciente_endereco_coibgemunicipio', 'paciente_endereco_copais',
           'paciente_endereco_nmmunicipio', 'paciente_endereco_nmpais',
           'paciente_endereco_uf', 'paciente_endereco_cep',
           'paciente_nacionalidade_enumnacionalidade', 'estabelecimento_valor',
           'estabelecimento_razaosocial', 'estalecimento_nofantasia',
           'estabelecimento_municipio_codigo', 'estabelecimento_municipio_nome',
           'estabelecimento_uf', 'vacina_grupoatendimento_codigo',
           'vacina_grupoatendimento_nome', 'vacina_categoria_codigo',
           'vacina_categoria_nome', 'vacina_lote', 'vacina_fabricante_nome',
           'vacina_fabricante_referencia', 'vacina_dataaplicacao',
           'vacina_descricao_dose', 'vacina_codigo', 'vacina_nome',
           'sistema_origem', 'data_importacao_rnds', 'id_sistema_origem'],
          dtype='object')




```python
# 3) Nesse DataFrame faça uma contagem do campo vacina_categoria_nome.

print('Total de vacinas')


df_menor['vacina_categoria_nome'].value_counts()


```

    Total de vacinas
    




    Povos Indígenas                     33
    Trabalhadores de Saúde               9
    Povos e Comunidades Tradicionais     9
    Comorbidades                         2
    Faixa Etária                         1
    Name: vacina_categoria_nome, dtype: int64




```python
# 4) a partir da lista de colunas, escolha somente aquelas que são referentes ao estabelecimento, faça uma lista com esses valores.

lista_variaveis = ['estabelecimento_valor',
       'estabelecimento_razaosocial', 'estalecimento_nofantasia',
       'estabelecimento_municipio_codigo', 'estabelecimento_municipio_nome',
       'estabelecimento_uf']
df_menor_lista = df_menor.loc[:,lista_variaveis]

print('Lista com os nomes dos estabelecimentos:')
lista_variaveis
```

    Lista com os nomes dos estabelecimentos:
    




    ['estabelecimento_valor',
     'estabelecimento_razaosocial',
     'estalecimento_nofantasia',
     'estabelecimento_municipio_codigo',
     'estabelecimento_municipio_nome',
     'estabelecimento_uf']




```python
# 5) usando o método .loc, selecione somente essas variáveis
df_menor_lista = df_menor_lista.drop_duplicates()
df_menor_lista.shape

df_menor_lista.loc[:,lista_variaveis]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>estabelecimento_valor</th>
      <th>estabelecimento_razaosocial</th>
      <th>estalecimento_nofantasia</th>
      <th>estabelecimento_municipio_codigo</th>
      <th>estabelecimento_municipio_nome</th>
      <th>estabelecimento_uf</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1567</th>
      <td>2001314</td>
      <td>PREFEITURA MUNICIPAL DE EPITACIOLANDIA</td>
      <td>ESF JOAO ALVES DA SILVA</td>
      <td>120025</td>
      <td>EPITACIOLANDIA</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>6250</th>
      <td>6917291</td>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
      <td>DEPARTAMENTO DE VIGILANCIA EPIDEMIOLOGICA E AM...</td>
      <td>120040</td>
      <td>RIO BRANCO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>9569</th>
      <td>6159087</td>
      <td>PREFEITURA MUNICIPAL DE CRUZEIRO DO SUL</td>
      <td>SECRETARIA MUNICIPAL DE SAUDE DE CRUZEIRO DO SUL</td>
      <td>120020</td>
      <td>CRUZEIRO DO SUL</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>11338</th>
      <td>2000040</td>
      <td>PREFEITURA MUNICIPAL DE FEIJO</td>
      <td>CENTRO DE SAUDE DIAMANTINO MACEDO</td>
      <td>120030</td>
      <td>FEIJO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>15144</th>
      <td>7625855</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
      <td>POLO BASE DE MARECHAL THAUMATURGO</td>
      <td>120035</td>
      <td>MARECHAL THAUMATURGO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>17153</th>
      <td>6748759</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
      <td>POLO BASE DE FEIJO</td>
      <td>120030</td>
      <td>FEIJO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>18361</th>
      <td>6308740</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
      <td>POLO BASE DE PORTO WALTER</td>
      <td>120039</td>
      <td>PORTO WALTER</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>18608</th>
      <td>2001748</td>
      <td>PREFEITURA MUNICIPAL DE PORTO WALTER</td>
      <td>UBS VICENTE VARELA DE ALMEIDA</td>
      <td>120039</td>
      <td>PORTO WALTER</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>20204</th>
      <td>6917682</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
      <td>POLO BASE DE CRUZEIRO DO SUL</td>
      <td>120020</td>
      <td>CRUZEIRO DO SUL</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>21119</th>
      <td>6428940</td>
      <td>PREFEITURA MUNICIPAL DE ASSIS BRASIL</td>
      <td>POLO BASE DE ASSIS BRASIL</td>
      <td>120005</td>
      <td>ASSIS BRASIL</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>29127</th>
      <td>6612385</td>
      <td>PREFEITURA MUNICIPAL DE TARAUACA</td>
      <td>UNIDADE ASSISTENCIAL A SAUDE INDIGENA DE TARAU...</td>
      <td>120060</td>
      <td>TARAUACA</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>57405</th>
      <td>9648968</td>
      <td>DISTRITO SANITARIO ESPECIAL DE SAUDE INDIGENA ...</td>
      <td>POLO INDIGENA DE MANOEL URBANO</td>
      <td>120034</td>
      <td>MANOEL URBANO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>61131</th>
      <td>6430201</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO JURUA</td>
      <td>POLO BASE INDIGENA</td>
      <td>120032</td>
      <td>JORDAO</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>68290</th>
      <td>6955525</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
      <td>POLO BASE DE MANCIO LIMA</td>
      <td>120033</td>
      <td>MANCIO LIMA</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>69882</th>
      <td>5336171</td>
      <td>SECRETARIA DE ESTADO DE SAUDE DO ACRE</td>
      <td>HOSPITAL REGIONAL DO JURUA</td>
      <td>120020</td>
      <td>CRUZEIRO DO SUL</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>70881</th>
      <td>6697151</td>
      <td>MINISTERIO DA SAUDE</td>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO PURUS</td>
      <td>120050</td>
      <td>SENA MADUREIRA</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>101402</th>
      <td>3323307</td>
      <td>PREFEITURA MUNICIPAL DE PORTO ACRE</td>
      <td>UNIDADE DE SAUDE DA FAMILIA ALVARO ARAUJO NOBRE</td>
      <td>120080</td>
      <td>PORTO ACRE</td>
      <td>AC</td>
    </tr>
    <tr>
      <th>140895</th>
      <td>7123043</td>
      <td>PREFEITURA MUNICIPAL DE JORDAO</td>
      <td>SAUDE DA FAMILIA RIBEIRINHA</td>
      <td>120032</td>
      <td>JORDAO</td>
      <td>AC</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 6) Aplique o método .drop_duplicates e crie uma lista com uma linha para cada estabelecimento, com os dados do estabelecimento

df_menor_lista = df_menor_lista['estabelecimento_razaosocial'].drop_duplicates()
df_menor_lista.reset_index(drop=True, inplace=True)
df_menor_lista.index += 1
df_menor_lista.to_frame()

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>estabelecimento_razaosocial</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>PREFEITURA MUNICIPAL DE EPITACIOLANDIA</td>
    </tr>
    <tr>
      <th>2</th>
      <td>PREFEITURA MUNICIPAL DE RIO BRANCO</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PREFEITURA MUNICIPAL DE CRUZEIRO DO SUL</td>
    </tr>
    <tr>
      <th>4</th>
      <td>PREFEITURA MUNICIPAL DE FEIJO</td>
    </tr>
    <tr>
      <th>5</th>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO RIO ...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>PREFEITURA MUNICIPAL DE PORTO WALTER</td>
    </tr>
    <tr>
      <th>7</th>
      <td>PREFEITURA MUNICIPAL DE ASSIS BRASIL</td>
    </tr>
    <tr>
      <th>8</th>
      <td>PREFEITURA MUNICIPAL DE TARAUACA</td>
    </tr>
    <tr>
      <th>9</th>
      <td>DISTRITO SANITARIO ESPECIAL DE SAUDE INDIGENA ...</td>
    </tr>
    <tr>
      <th>10</th>
      <td>DISTRITO SANITARIO ESPECIAL INDIGENA ALTO JURUA</td>
    </tr>
    <tr>
      <th>11</th>
      <td>SECRETARIA DE ESTADO DE SAUDE DO ACRE</td>
    </tr>
    <tr>
      <th>12</th>
      <td>MINISTERIO DA SAUDE</td>
    </tr>
    <tr>
      <th>13</th>
      <td>PREFEITURA MUNICIPAL DE PORTO ACRE</td>
    </tr>
    <tr>
      <th>14</th>
      <td>PREFEITURA MUNICIPAL DE JORDAO</td>
    </tr>
  </tbody>
</table>
</div>


