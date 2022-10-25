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
  
## ✔️ Técnicas, processos e tecnologias utilizadas
  
  
   - `1 - Coleta de dados` Em primeiro momento para viabilidade do projeto foi feita uma coleta dos dados, tanto da corrente que a fonte fornecia, medida
   por um amperímetro e o a corrente mostrada no display, a temperatura medida por uma câmera termica e e todos os dados em relação ao tempo que a fonte estava
   ligada. Esses dados foram coletados em vários níveis de corrente dependendo da quantidade de corrente que a fonte conseguia aguentar,
   e armazenados em uma planilha (Clique [aqui](https://github.com/lfelipesal/Projeto-corrente/blob/main/dados-amostras) 
   para ver os dados coletados).
  
  
  
  - `2 - Análise dos dados` Com os dados em mãos foi feita uma análise gráfica relacionando a diferença que
  a corrente sofria entre o valor medido pela fonte, ou seja, o valor com a soma do erro, e a corrente medida pelo amperímetro,
  em relação ao tempo que ela era aquecida. Utilizando a ferramenta gratuita de análise gráfica chamada [SciDAVis](https://scidavis.sourceforge.net/),
  foi observado um comportamento linear da curva, sabendo sobre esse comportamento o método de implementação de correção poderia seguir por inumeros caminhos,
  tanto pela interpolação dos dados gerando uma curva de correção, ou então uma derivação dos dados para obter uma constante de correção. 
  Nesse projeto optamos por interpolar os dados e assim criar uma curva de correção com base em uma porcentagem de amostra de corrente inicial, 
     pelo fato de cada fonte possuir uma inclinação diferente em comparação da corrente que ela suporta.
  
      <details>
            <summary><b>Gráficos<b/></summary>
              
     ![graf com 30 25 e 20 amper em relação a temp do filtro](https://user-images.githubusercontent.com/93229568/197697355-abb5a8b1-e0c3-4f2d-b39d-c9a020c774b1.jpg)
              
        
     ![graf com 30 25 e 20 amper em relação a temp UPS](https://user-images.githubusercontent.com/93229568/197697383-75be91f9-527e-43a8-b273-bf3278a64d48.jpg)

      </details>
  
  - `3 - Interpolação` Utilizando algumas biblioteca do Python para interpolação de dados, o programa conseguiu realizar uma curva de correção para 
  cada tipo de fonte dependendo dos dados de entrada. As curvas são criadas colhendo 10% da corrente inicial, e em sequência 10 amostras de correntes erradas 
  durante 10 minutos, e no momento posterior já com a curva de correção pronta os próximos valores que a fonte fornecer de corrente, entra na margem de correção
  resultando em um valor com +/- 10% de erro em comparação ao valor real de corrente.
        <details>
            <summary><b>Gráficos gerado pelo programa<b/></summary>
            
       ![graf em python](https://user-images.githubusercontent.com/93229568/197697549-c837b6e2-1295-4068-b63e-db7e03798583.jpg)

        </details>
          
  - `4 - Implementação` Para colocar essa nova funcionalidade no display, séria necessário o estudo do seu código e do seu hardware de modo esquemático, ou seja,
          para criar um ambiente simulado de desenvolvimento utilizando o Proteus 8, e o microcontrolador STM32 era preciso ter acesso as documentações 
          dos dispositivos, porém a empresa não demonstrou ser solicita para fornecer esses tipos de documentos, resultando no fim do projeto por conflito 
          de interesse. 
  
<details>
  <summary><b>Tecnologias utilizadas<b/></summary>
    
  - `Python 3` Linguagem inicial da modelagem do problema.
  - `Jupyter` Notebook: Framework para implementação inicial.
  - `SciDAVis` Ferramenta de análise gráfica.
    
</details>
  
## 📁 Acesso ao projeto
  
  Para acessar o Jupyter Notebook do projeto, onde possuí toda codificação do programa, clique [aqui](https://github.com/lfelipesal/Projeto-corrente/blob/main/codigo/JFA-ultimaAtt.ipynb)
