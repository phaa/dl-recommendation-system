# Sistema de recomendação visual

Esse projeto foi desenvolvido durante o treinamento da DIO com a BairesDev para machine learning na seção sobre deep learning.

<p align="center">
 <img src="https://yt3.googleusercontent.com/A2PDGXF6Rw73xB0nNNY040ulT4EAXC_dzjDRnrfiY8vpt3LKbaUOD79u6yEAiHf9JIAgM1LGfw=s900-c-k-c0x00ffffff-no-rj" title="book" width="180" />
</p>

O intuito desse projeto é criar um sistema de recomendação de itens de forma puramente visual, utilizando redes neurais para extração de embbedings.

---

### Como funciona?
1. Utilizamos uma rede VGG16, que, por ser pré treinada no imagenet, já serve como uma boa extratora de features.
2. Usamos a rede para extrair as features de todas as imagens do dataset
3. Armazenamos os vetores de embbeddings em um dicionário (simulando um banco de dados especializado)
4. Carregamos uma imagem de exemplo e extraímos suas features
5. Comparamos as embbedings da imagem carregada com as demais armazenadas usando a medida de distância vetorial cosine
6. Recuperamos as imagens mais parecidas e plotamos, sendo as mais parecidas à esquerda

---

### Qual o diferencial?
Esse projeto pode ser aplicado como um sistema de sugestão puramente visual, ou seja, dispensa qualquer necessidade de dados adicionais sobre o produto para que sejam achados produtos que interessem o usuário.

---

### Melhores resultados após uma busca
<p align="center">
 <img src="https://github.com/phaa/dl-recommendation-system/blob/main/Captura%20de%20tela%20de%202025-04-08%2022-45-55.png" title="book" width="800" />
</p>
