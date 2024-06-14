# prova2-m6 - Sistema de detecção de facez PIFA

## Questões técnicas:

### 1. Descreva de maneira concisa (um parágrafo no máximo) o funcionamento do método de detecção escolhido.

    O método escolhido foi o Haar Cascade devido ao seu pré-treinamento com faces. Ele funciona a partir da intensidade de pixels em uma função cascade e é treinado a partir do reforço entre muitas imagens negativas e positivas.


### 2. Considere as seguintes alternativas para resolver o problema de detecção de faces: HAAR Cascade, CNN, NN Linear, Filtros de correlação cruzada. Classifique-os (coloque em ordem) em termos de viabilidade técnica (se é possível resolver o problema), facilidade de implementação e versatilidade da solução. Justifique sua classificação.
    Em termos de viabilidade técnica, acredito que o haar cascade seja a melhor opção devido a uma grande base de treinamento e a extração de características, dado que a angulação dos rostos não se modifica tanto e o modelo de haar cascade frontal consegue identificar bem. Já o CNN também traz uma boa detecção devido à sua camada de convolução poder extrair diversas informações como formato do rosto, nariz(que não possui atualmente no haar cascade). O filtro de correlação cruzada, ao fazer uma convolução da imagem com a região detectada, pode ser eficaz para alguns frames e para essse vídeo específico, mas para outros casos, como uma pessoa girando, se movimentando com o corpo ou muitas pessoas diferentes a serem identificadas, essa alternativa não seria tão interessante. O NN linear,por fim, seria o método menos eficaz em termos de viabilidade técnica, pois ele não funciona muito bem com imagens, dado qa=ue seu funcionamento se dá pela multiplicação dos pesos pelos viéses, o que dificulta de extrair informações de imagens e requer um tempo de treino muito grande para uma eficácia não tão boa. Portanto, no questio viabilidade técnica, o ranking seria:
        - 1° : Haar Cascade
        - 2° : Correlação cruzada
        - 3° : CNN
        - 4° : NN linear

    Em relação à facilidade de implementação, o haar cascade ganha notoriamente das outras alternativas, dado que o modelo já vem treinado e para aplicá-lo, basta rodar o meodo  detectmultiscale` com o modelo em xml, o que o torna fácil de implementar e fácil de executar, pois seu arquivo é pequeno em comparação com os demais. A correlação cruzada se torna de facil a média implementação, dado que é preciso ter uma imagem de referência para convolucionar e aplicar essa convolução achando o máximo da correlação e depois detectando essa região na imagem original. Nesse caso, requer vários passos e mais raciocínio matemático envolvido. A NN linear possui uma implementação difícil nesse caso pois ela depende de um dataset para ser treinado, um dataset que possua as identificações, não apenas as imagens, e os treinamentos para alcançar um bom resultado requerem bastante épocas a serem rodadas para ajustas os pesos. Além disso, para ser capaz de identificar as faces, esse modelo de NN linear precisaria ser robusto e com muitas camadas ocultas. Por fim,  CNN possui a implementação mais dificil pois requer um dataset treinado, assim como a NN linear, requer uma capacidade de processamento alta para realizar o pooling e a camada de convolução. Portanto, a depender do que se quer ser extraido, do tamanho da imagem e do dataset e do modelo escolhido, a CNN pode ser mais dificil de ser implementada pois a depender do número de épocas rodados para alcançar a melhor precisão, pode demandar bastantye processaamento da máquina, sendo mais "pesado" do que a NN linear. Assim, o rankign de facilidade é:
        - 1° : Haar Cascade
        - 2° : Correlação cruzada
        - 3° : NN linear
        - 4° : CNN

    Em relação a versatilidade, a CNN ganha notoriamente das outras por ter uma capacidade de aprendizado maior e mais robusto que as outrasm dado que extrai muitas características a partir da convolução, como textura, borda da imagem, traços, portanto, ela é inclusive uma das mais utilizadas na detecção de objetos e pessoas em imagens. Em segundo lugar, a NN linear possui uam grande versatilidade por poder ser utilizada não só em imagens mas em operadores lógicos, por exemplo. Em terceiro lugar seriaa correlação cruzada por poder detectar outras coisaa além da face e em ultismo seria o haar cascade por detectar apenas faces e algumas caracteristicas.

### 3. Considerando as mesmas alternativas acima, faça uma nova classificação considerando a viabilidade técnica para detecção de emoções através da imagem de uma face.
    Para detectar emoções, o modelo mais adequado seria o cnn devido a sua versatilidade e capacidade de detectar muitas características, sendo elas detalhes dos rostos das faces detectadas. Em segundo lugar seria o haar cascade com um dataset treinado especificamente para isso.EM terceirto lugar seria a correlação cruzada, pois apesar da pouca versatilidade, para esse caso, ela detectaria a correlação da estrutura dos tipos de emoções e poderia relacionar a triteza com a falta de sorriso, por exemplos, detectando alterações das emoções. por fim,o haar cascade 


### 4. A solução apresentada ou qualquer outra das que foram listadas na questão 2.2. tem a capacidade de considerar variações de um frame para outro (e.g. perceber que em um frame a pessoa está feliz e isso influenciar na detecção do próximo frame)? Se não, quais alterações poderiam ser feitas para que isso seja possível?
        ele nap tem acapacidade de detectar diferencas ntre um frame e outro e melhor maneira de alterar para prever isso sera o filtro de kalman para a prtir da previsão, poder ver 




## Projeto

### Como executar:

Para rodar o modelo, entre no notebook do Google Colab a partir desses link :

https://colab.research.google.com/drive/1Xj2Wv0xEXvufnLIV1QTnohN0km3yHBYd?usp=sharing

Lá vocês terá todas as instruções detalhadas sobre como executar e o que fazer para ver o vídeo com o resultado da detecção.


Além disso, segue o vídeo como resutado final aqui nesse repósitório, o arquivo new_video28.avi
