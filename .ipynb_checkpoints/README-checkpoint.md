# Tarefa 01

- Leia os enunciados com atenção
- Saiba que pode haver mais de uma resposta correta
- Insira novas células de código sempre que achar necessário
- Em caso de dúvidas, procure os tutores
- Divirta-se :)

#### 1)  crie uma série do pandas a partir de uma lista com os dados abaixo:

Em um estudo sobre alteração na tempreatura global, A NASA disponibiliza dados de diferenças de de temperatura média da superfície terrestre relativos às médias de temperatura entre 1951 e 1980. Os dados originais podem ser vistos no site da NASA/GISS, e estão dispostos a cada década na tabela abaixo.

|ano|anomalia termica|
|:-:|:----:|
| 1900 | -0.08 |
| 1920 | -0.27 |
| 1940 | 0.12 |
| 1960 | -0.03 |
| 1980 | 0.26 |
| 2000 | 0.40 |
| 2020 | 1.02 |

Crie uma séries do Pandas a partir de uma lista com esses dados.


```python
import pandas as pd
import numpy as np
```


```python
# Seu código aqui
dados = [-0.08, -0.27, 0.12, -0.03, 0.26, 0.40, 1.02]
temp = pd.Series(dados)
temp
```




    0   -0.08
    1   -0.27
    2    0.12
    3   -0.03
    4    0.26
    5    0.40
    6    1.02
    dtype: float64



#### 2) Coloque os anos nos índices conforme a tabela.


```python
temp.index
```




    RangeIndex(start=0, stop=7, step=1)




```python
# seu código aqui
temp = pd.Series([-0.08, -0.27, 0.12, -0.03, 0.26, 0.40, 1.02],
                index=[1900, 1920, 1940, 1960, 1980, 2000, 2020])
temp
```




    1900   -0.08
    1920   -0.27
    1940    0.12
    1960   -0.03
    1980    0.26
    2000    0.40
    2020    1.02
    dtype: float64



#### 3) A partir do dicionário abaixo, crie uma séries do Pandas:


```python
dic_temperaturas = {1900: -.08, 1920: -.27, 1940: .12, 1960: -.03, 1980: .26, 2000: .40, 2020: 1.02}

# seu código aqui
temp_series = pd.Series(dic_temperaturas)
temp_series
```




    1900   -0.08
    1920   -0.27
    1940    0.12
    1960   -0.03
    1980    0.26
    2000    0.40
    2020    1.02
    dtype: float64



#### 4) Transforme o ndarray abaixo em um dataframe. 
O numpy é capaz de gerar arrays n-dimensionais com números pseudo-aleatórios de acordo com uma variedade de distribuições, como no exemplo abaixo. Transforme esse nd-array em um DataFrame.


```python
arr = np.random.normal(100, 10, (20,3))

# seu código aqui
df = pd.DataFrame(arr, columns=['A', 'B', 'C'])
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>103.343260</td>
      <td>103.395368</td>
      <td>99.576471</td>
    </tr>
    <tr>
      <th>1</th>
      <td>114.205061</td>
      <td>103.098137</td>
      <td>85.966622</td>
    </tr>
    <tr>
      <th>2</th>
      <td>69.545354</td>
      <td>90.266847</td>
      <td>113.586802</td>
    </tr>
    <tr>
      <th>3</th>
      <td>100.270542</td>
      <td>92.193015</td>
      <td>85.165505</td>
    </tr>
    <tr>
      <th>4</th>
      <td>97.683422</td>
      <td>99.013672</td>
      <td>110.002333</td>
    </tr>
    <tr>
      <th>5</th>
      <td>110.621325</td>
      <td>106.788609</td>
      <td>100.478386</td>
    </tr>
    <tr>
      <th>6</th>
      <td>90.203504</td>
      <td>119.807902</td>
      <td>69.992269</td>
    </tr>
    <tr>
      <th>7</th>
      <td>118.057708</td>
      <td>104.037779</td>
      <td>100.711517</td>
    </tr>
    <tr>
      <th>8</th>
      <td>95.022144</td>
      <td>88.976811</td>
      <td>105.002542</td>
    </tr>
    <tr>
      <th>9</th>
      <td>99.946995</td>
      <td>92.719883</td>
      <td>102.126863</td>
    </tr>
    <tr>
      <th>10</th>
      <td>94.502136</td>
      <td>114.203425</td>
      <td>95.106606</td>
    </tr>
    <tr>
      <th>11</th>
      <td>86.371067</td>
      <td>102.669055</td>
      <td>110.551369</td>
    </tr>
    <tr>
      <th>12</th>
      <td>80.291366</td>
      <td>95.282705</td>
      <td>117.944834</td>
    </tr>
    <tr>
      <th>13</th>
      <td>90.037921</td>
      <td>113.924869</td>
      <td>92.674390</td>
    </tr>
    <tr>
      <th>14</th>
      <td>107.997459</td>
      <td>102.570157</td>
      <td>103.793515</td>
    </tr>
    <tr>
      <th>15</th>
      <td>90.717468</td>
      <td>109.329761</td>
      <td>94.523770</td>
    </tr>
    <tr>
      <th>16</th>
      <td>89.406957</td>
      <td>110.556718</td>
      <td>94.613154</td>
    </tr>
    <tr>
      <th>17</th>
      <td>76.592852</td>
      <td>122.056004</td>
      <td>106.771667</td>
    </tr>
    <tr>
      <th>18</th>
      <td>100.515621</td>
      <td>95.273465</td>
      <td>87.604137</td>
    </tr>
    <tr>
      <th>19</th>
      <td>79.979441</td>
      <td>111.928110</td>
      <td>95.771747</td>
    </tr>
  </tbody>
</table>
</div>



#### 5) Nomeie os índices das linhas com inteiros de 1 a 20, e as colunas com os nomes "x1", "x2", e "x3" respectivamente.


```python
#seu código aqui
df.index = range(1, 21)
df.columns = ['x1', 'x2', 'x3']
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
      <th>x1</th>
      <th>x2</th>
      <th>x3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>103.343260</td>
      <td>103.395368</td>
      <td>99.576471</td>
    </tr>
    <tr>
      <th>2</th>
      <td>114.205061</td>
      <td>103.098137</td>
      <td>85.966622</td>
    </tr>
    <tr>
      <th>3</th>
      <td>69.545354</td>
      <td>90.266847</td>
      <td>113.586802</td>
    </tr>
    <tr>
      <th>4</th>
      <td>100.270542</td>
      <td>92.193015</td>
      <td>85.165505</td>
    </tr>
    <tr>
      <th>5</th>
      <td>97.683422</td>
      <td>99.013672</td>
      <td>110.002333</td>
    </tr>
    <tr>
      <th>6</th>
      <td>110.621325</td>
      <td>106.788609</td>
      <td>100.478386</td>
    </tr>
    <tr>
      <th>7</th>
      <td>90.203504</td>
      <td>119.807902</td>
      <td>69.992269</td>
    </tr>
    <tr>
      <th>8</th>
      <td>118.057708</td>
      <td>104.037779</td>
      <td>100.711517</td>
    </tr>
    <tr>
      <th>9</th>
      <td>95.022144</td>
      <td>88.976811</td>
      <td>105.002542</td>
    </tr>
    <tr>
      <th>10</th>
      <td>99.946995</td>
      <td>92.719883</td>
      <td>102.126863</td>
    </tr>
    <tr>
      <th>11</th>
      <td>94.502136</td>
      <td>114.203425</td>
      <td>95.106606</td>
    </tr>
    <tr>
      <th>12</th>
      <td>86.371067</td>
      <td>102.669055</td>
      <td>110.551369</td>
    </tr>
    <tr>
      <th>13</th>
      <td>80.291366</td>
      <td>95.282705</td>
      <td>117.944834</td>
    </tr>
    <tr>
      <th>14</th>
      <td>90.037921</td>
      <td>113.924869</td>
      <td>92.674390</td>
    </tr>
    <tr>
      <th>15</th>
      <td>107.997459</td>
      <td>102.570157</td>
      <td>103.793515</td>
    </tr>
    <tr>
      <th>16</th>
      <td>90.717468</td>
      <td>109.329761</td>
      <td>94.523770</td>
    </tr>
    <tr>
      <th>17</th>
      <td>89.406957</td>
      <td>110.556718</td>
      <td>94.613154</td>
    </tr>
    <tr>
      <th>18</th>
      <td>76.592852</td>
      <td>122.056004</td>
      <td>106.771667</td>
    </tr>
    <tr>
      <th>19</th>
      <td>100.515621</td>
      <td>95.273465</td>
      <td>87.604137</td>
    </tr>
    <tr>
      <th>20</th>
      <td>79.979441</td>
      <td>111.928110</td>
      <td>95.771747</td>
    </tr>
  </tbody>
</table>
</div>



#### 6) No DataFrame do exercício 5, crie uma nova coluna como sendo a média das três colunas, e dê a ela o nome de "media" (não recomendo colocar acentos em nomes de variáveis).


```python
# seu código aqui
df['media'] = (df['A'] + df['B'] + df['C']) / 3
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>media</th>
      <th>log_med</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>103.343260</td>
      <td>103.395368</td>
      <td>99.576471</td>
      <td>102.105033</td>
      <td>4.626002</td>
    </tr>
    <tr>
      <th>1</th>
      <td>114.205061</td>
      <td>103.098137</td>
      <td>85.966622</td>
      <td>101.089940</td>
      <td>4.616011</td>
    </tr>
    <tr>
      <th>2</th>
      <td>69.545354</td>
      <td>90.266847</td>
      <td>113.586802</td>
      <td>91.133001</td>
      <td>4.512320</td>
    </tr>
    <tr>
      <th>3</th>
      <td>100.270542</td>
      <td>92.193015</td>
      <td>85.165505</td>
      <td>92.543021</td>
      <td>4.527674</td>
    </tr>
    <tr>
      <th>4</th>
      <td>97.683422</td>
      <td>99.013672</td>
      <td>110.002333</td>
      <td>102.233142</td>
      <td>4.627256</td>
    </tr>
    <tr>
      <th>5</th>
      <td>110.621325</td>
      <td>106.788609</td>
      <td>100.478386</td>
      <td>105.962773</td>
      <td>4.663088</td>
    </tr>
    <tr>
      <th>6</th>
      <td>90.203504</td>
      <td>119.807902</td>
      <td>69.992269</td>
      <td>93.334558</td>
      <td>4.536190</td>
    </tr>
    <tr>
      <th>7</th>
      <td>118.057708</td>
      <td>104.037779</td>
      <td>100.711517</td>
      <td>107.602335</td>
      <td>4.678442</td>
    </tr>
    <tr>
      <th>8</th>
      <td>95.022144</td>
      <td>88.976811</td>
      <td>105.002542</td>
      <td>96.333832</td>
      <td>4.567820</td>
    </tr>
    <tr>
      <th>9</th>
      <td>99.946995</td>
      <td>92.719883</td>
      <td>102.126863</td>
      <td>98.264581</td>
      <td>4.587664</td>
    </tr>
    <tr>
      <th>10</th>
      <td>94.502136</td>
      <td>114.203425</td>
      <td>95.106606</td>
      <td>101.270722</td>
      <td>4.617797</td>
    </tr>
    <tr>
      <th>11</th>
      <td>86.371067</td>
      <td>102.669055</td>
      <td>110.551369</td>
      <td>99.863830</td>
      <td>4.603808</td>
    </tr>
    <tr>
      <th>12</th>
      <td>80.291366</td>
      <td>95.282705</td>
      <td>117.944834</td>
      <td>97.839635</td>
      <td>4.583330</td>
    </tr>
    <tr>
      <th>13</th>
      <td>90.037921</td>
      <td>113.924869</td>
      <td>92.674390</td>
      <td>98.879060</td>
      <td>4.593897</td>
    </tr>
    <tr>
      <th>14</th>
      <td>107.997459</td>
      <td>102.570157</td>
      <td>103.793515</td>
      <td>104.787044</td>
      <td>4.651930</td>
    </tr>
    <tr>
      <th>15</th>
      <td>90.717468</td>
      <td>109.329761</td>
      <td>94.523770</td>
      <td>98.190333</td>
      <td>4.586908</td>
    </tr>
    <tr>
      <th>16</th>
      <td>89.406957</td>
      <td>110.556718</td>
      <td>94.613154</td>
      <td>98.192276</td>
      <td>4.586928</td>
    </tr>
    <tr>
      <th>17</th>
      <td>76.592852</td>
      <td>122.056004</td>
      <td>106.771667</td>
      <td>101.806841</td>
      <td>4.623077</td>
    </tr>
    <tr>
      <th>18</th>
      <td>100.515621</td>
      <td>95.273465</td>
      <td>87.604137</td>
      <td>94.464407</td>
      <td>4.548223</td>
    </tr>
    <tr>
      <th>19</th>
      <td>79.979441</td>
      <td>111.928110</td>
      <td>95.771747</td>
      <td>95.893100</td>
      <td>4.563234</td>
    </tr>
  </tbody>
</table>
</div>



#### 7) No DataFrame do exercício 6, crie uma nova coluna chamada "log_med", contendo o logaritmo natural da média calculada no exercício 6 <br>


```python
# seu código aqui
df['media'] = (df['A'] + df['B'] + df['C']) / 3
df['log_med'] = np.log(df['media'])

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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>media</th>
      <th>log_med</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>103.343260</td>
      <td>103.395368</td>
      <td>99.576471</td>
      <td>102.105033</td>
      <td>4.626002</td>
    </tr>
    <tr>
      <th>1</th>
      <td>114.205061</td>
      <td>103.098137</td>
      <td>85.966622</td>
      <td>101.089940</td>
      <td>4.616011</td>
    </tr>
    <tr>
      <th>2</th>
      <td>69.545354</td>
      <td>90.266847</td>
      <td>113.586802</td>
      <td>91.133001</td>
      <td>4.512320</td>
    </tr>
    <tr>
      <th>3</th>
      <td>100.270542</td>
      <td>92.193015</td>
      <td>85.165505</td>
      <td>92.543021</td>
      <td>4.527674</td>
    </tr>
    <tr>
      <th>4</th>
      <td>97.683422</td>
      <td>99.013672</td>
      <td>110.002333</td>
      <td>102.233142</td>
      <td>4.627256</td>
    </tr>
    <tr>
      <th>5</th>
      <td>110.621325</td>
      <td>106.788609</td>
      <td>100.478386</td>
      <td>105.962773</td>
      <td>4.663088</td>
    </tr>
    <tr>
      <th>6</th>
      <td>90.203504</td>
      <td>119.807902</td>
      <td>69.992269</td>
      <td>93.334558</td>
      <td>4.536190</td>
    </tr>
    <tr>
      <th>7</th>
      <td>118.057708</td>
      <td>104.037779</td>
      <td>100.711517</td>
      <td>107.602335</td>
      <td>4.678442</td>
    </tr>
    <tr>
      <th>8</th>
      <td>95.022144</td>
      <td>88.976811</td>
      <td>105.002542</td>
      <td>96.333832</td>
      <td>4.567820</td>
    </tr>
    <tr>
      <th>9</th>
      <td>99.946995</td>
      <td>92.719883</td>
      <td>102.126863</td>
      <td>98.264581</td>
      <td>4.587664</td>
    </tr>
    <tr>
      <th>10</th>
      <td>94.502136</td>
      <td>114.203425</td>
      <td>95.106606</td>
      <td>101.270722</td>
      <td>4.617797</td>
    </tr>
    <tr>
      <th>11</th>
      <td>86.371067</td>
      <td>102.669055</td>
      <td>110.551369</td>
      <td>99.863830</td>
      <td>4.603808</td>
    </tr>
    <tr>
      <th>12</th>
      <td>80.291366</td>
      <td>95.282705</td>
      <td>117.944834</td>
      <td>97.839635</td>
      <td>4.583330</td>
    </tr>
    <tr>
      <th>13</th>
      <td>90.037921</td>
      <td>113.924869</td>
      <td>92.674390</td>
      <td>98.879060</td>
      <td>4.593897</td>
    </tr>
    <tr>
      <th>14</th>
      <td>107.997459</td>
      <td>102.570157</td>
      <td>103.793515</td>
      <td>104.787044</td>
      <td>4.651930</td>
    </tr>
    <tr>
      <th>15</th>
      <td>90.717468</td>
      <td>109.329761</td>
      <td>94.523770</td>
      <td>98.190333</td>
      <td>4.586908</td>
    </tr>
    <tr>
      <th>16</th>
      <td>89.406957</td>
      <td>110.556718</td>
      <td>94.613154</td>
      <td>98.192276</td>
      <td>4.586928</td>
    </tr>
    <tr>
      <th>17</th>
      <td>76.592852</td>
      <td>122.056004</td>
      <td>106.771667</td>
      <td>101.806841</td>
      <td>4.623077</td>
    </tr>
    <tr>
      <th>18</th>
      <td>100.515621</td>
      <td>95.273465</td>
      <td>87.604137</td>
      <td>94.464407</td>
      <td>4.548223</td>
    </tr>
    <tr>
      <th>19</th>
      <td>79.979441</td>
      <td>111.928110</td>
      <td>95.771747</td>
      <td>95.893100</td>
      <td>4.563234</td>
    </tr>
  </tbody>
</table>
</div>


