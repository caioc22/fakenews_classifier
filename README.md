# fakenews_classifier
Classificador de notícias falsas, projeto desenvolvido para a disciplina de Natural Language Processing para o curso de Técnologo em Ciência de Dados.
## Objetivo
Criar um modelo que classifique notícias falsas e verdadeiras que consiga atingir uma acurácia de pelo menos 85%, utilizando o corpus Fake.br (https://github.com/roneysco/Fake.br-Corpus.git) para treinamento e validação.

## Abordagens
Diferente da abordagem apresentada no artigo base https://arxiv.org/pdf/2309.11052.pdf dos mesmos criadores do corpus Fake.br, esse projeto aplicou a modelagem semântica das sentenças usando camadas *Embedding* criadas com os excertos *tokenizados* em um formato padrão (gerando efeito equivalente a truncagem de textos, para evitar que o modelo classifique por comprimento da sentença ao invés do conteúdo), alimentando uma camada Gated Recurrent Unit uni-direcional para aprendizado e classificação. Foram também testados abordagens com modelos clássicos, porém o ganho de performance na abordagem neural foi significativo. Nenhuma etapa de balanceamento prévio foi necessária, pois o corpus já é balanceado.

## Conclusão
A modelo neural desenvolvido atingiu performance de 96.44%, porém a inferência demandou mais tempo e processamento, em comparação com os modelos clássicos. Os autores conseguiram acurácias ainda melhores neste desafio utilizando modelos clássicos e outras técnicas além do TF-IDF, como skip-grams e *cbow*.
