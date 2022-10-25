# Projeto de correção da corrente

Desenvolvido em Python, esse foi um projeto que desenvolvi em uma empresa que trabalhei para corrigir a 
corrente que o display da fonte gerenciável que eles fabricam mostra, percebendo que possuia uma relação linear entre 
a taxa de variação da temperatura e a taxa de variação entre a corrente medida e a corrente real. Consegui
interpolar os dados e obtendo assim uma função de correção para mostrar a corrente real no display.

<details>
  <summary><b>Apresentação feita para o engenheiro elétrico da empresa<b/></summary>
  
  ![Slide1](https://user-images.githubusercontent.com/93229568/197680465-4a2995fa-4e7a-47df-8c9a-a8572405f235.jpg)
  ![Slide2](https://user-images.githubusercontent.com/93229568/197680468-bc4b2ce9-2877-4c22-83b8-0abc59a1f2fc.jpg)
  ![Slide3](https://user-images.githubusercontent.com/93229568/197680469-33f1ea6e-c7ea-4858-8ed3-e17ca694e088.jpg)
  ![Slide4](https://user-images.githubusercontent.com/93229568/197680470-d08d8d35-d81e-4a3d-a29d-b753a4f4b5fa.jpg)
  ![Slide5](https://user-images.githubusercontent.com/93229568/197680459-dbb01c27-2304-400a-a448-77b7b934934e.jpg)
  ![Slide6](https://user-images.githubusercontent.com/93229568/197680463-c189fc2a-f064-4304-8ddd-89a0c53d5b5f.jpg)
    
</details>
  
## 🔨 Funcionalidades do projeto
  
  A principal função do software é a correção do erro que acontece na medição da corrente que ocorre quando a temperatura da fonte aumenta com o tempo.
  Então o programa faz a leitura da corrente de entrada projetando 10% de erro aceitavel para manipulação e interporlação dos próximos dados
  que ele irá receber, ou seja, guardando um valor base inicial para parâmetro de correção depois recebe uma sequência de 10 valores de medições erradas 
  no tempo de 15 minutos, e no momento posterior realiza a interpolação desses dados recebidos para criar uma curva de correção em base do valor inicialmente guardado.
  
## ✔️ Técnicas e tecnologias utilizadas
  
    - `1 - Coleta de dados` Em primeiro momento para viabilidade do projeto foi feita uma coleta dos dados, tanto da corrente que a fonte fornecia, medida
    por um amperímetro e o a corrente mostrada no display, a temperatura medida por uma câmera termica e e todos os dados em relação ao tempo que a fonte estava
    ligada. Esses dados foram coletados em vários níveis de corrente dependendo da quantidade de corrente que a fonte conseguia aguentar, e armazenados em uma planilha (Clique [aqui](https://github.com/lfelipesal/Projeto-corrente/blob/main/dados-amostras/Dados%20colatados.xlsx) para ver os dados coletados).
  
  
    - `2 - Análise dos dados` Com os dados em mãos foi feita uma análise gráfica relacionando a diferença que a corrente sofria entre o valor medido pela fonte, ou seja, o valor com a soma do erro, e a corrente medida pelo amperímetro, em relação ao tempo que ela era aquecida. Utilizando a ferramenta gratuita de análise gráfica chamada [SciDAVis](https://scidavis.sourceforge.net/), foi observado um comportamento linear da curva, sabendo sobre esse comportamento o método de implementação de correção poderia seguir por inumeros caminhos, tanto pela interpolação dos dados gerando uma curva de correção, ou então uma derivação dos dados para obter uma constante de correção. Nesse projeto optamos por interpolar os dados e assim criar uma curva de correção com base em uma porcentagem de amostra de corrente inicial, pelo fato de cada fonte possuir uma inclinação diferente em comparação da corrente que ela suporta.
    - <details>
        <summary><b>Gráficos<b/></summary>
          
  </details>
  
  - `3 - Interpolação`
  
<details>
  <summary><b>Tecnologias<b/></summary>
    
  - `Python 3` Linguagem inicial da modelagem do problema.
  - `Jupyter` Notebook: Framework para implementação inicial.
  - `SciDAVis` Ferramenta de análise gráfica.
    
</details>
