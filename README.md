# Previsão de Valor de Imóveis com Machine Learning

Este projeto utiliza **Machine Learning** para prever o valor de imóveis com base na metragem quadrada (m²) de cada imóvel. O modelo foi treinado utilizando um conjunto de dados simples e o algoritmo de aprendizado supervisionado, permitindo prever preços de imóveis a partir de um valor de metragem informado pelo usuário. O projeto foi desenvolvido com o framework **Streamlit**, facilitando a criação de uma interface interativa para o usuário.

## Tecnologias Utilizadas

- **Python 3.x**
- **Streamlit**: Framework para criação de interfaces web interativas com Python.
- **pandas**: Biblioteca para manipulação de dados.
- **pickle**: Para salvar e carregar o modelo treinado.
- **scikit-learn**: Biblioteca utilizada para a criação do modelo de machine learning (não mostrado no código, mas faz parte do pipeline de treinamento).

## Como Funciona

1. **Carregamento do Modelo**: O modelo já treinado é carregado a partir de um arquivo `.pkl` utilizando a biblioteca `pickle`.
   
2. **Entrada do Usuário**: A interface permite que o usuário insira o tamanho do imóvel em metros quadrados através de um campo interativo.

3. **Previsão de Preço**: Com base na metragem fornecida, o modelo calcula e retorna o valor estimado do imóvel.

4. **Interface Interativa**: Utilizando o Streamlit, o projeto possui uma interface amigável onde o usuário pode inserir os dados e obter a previsão em tempo real.

## Como Rodar o Projeto Localmente

### 1. Clone o repositório

```bash
git clone https://github.com/SEU_USUARIO/nome-do-repositorio.git
cd nome-do-repositorio

2. Instale as dependências
Para instalar as dependências necessárias, execute o seguinte comando:

bash
Copiar código
pip install -r requirements.txt
requirements.txt deve conter as bibliotecas necessárias como:

plaintext
Copiar código
streamlit
pandas
scikit-learn
3. Coloque o modelo treinado
Certifique-se de ter o arquivo do modelo treinado (modelo_treinado.pkl) na raiz do projeto. Caso ainda não tenha treinado o modelo, você precisará treinar um modelo com seus dados, utilizando scikit-learn (como uma regressão linear, por exemplo), e salvar o modelo com o pickle.

4. Rodar a aplicação
Após garantir que as dependências estão instaladas e o modelo treinado está presente, execute o comando:

bash
Copiar código
streamlit run app.py
Isso abrirá o aplicativo no seu navegador padrão, e você poderá interagir com a previsão de valor de imóveis.

Detalhes do Código
Modelo de Machine Learning: O código carrega um modelo previamente treinado e salva com pickle. Este modelo é utilizado para prever o valor de imóveis com base na metragem fornecida.

Função calcula_valor(metragem): Esta função recebe a metragem como entrada, cria um DataFrame com pandas e faz a previsão usando o modelo carregado.

Streamlit: Usado para criar a interface do usuário. Ele exibe:

Um campo para o usuário inserir a metragem do imóvel.
Um botão para calcular o valor do imóvel.
Uma mensagem de erro ou sucesso, dependendo do valor inserido.
Como Treinar o Modelo
Para treinar um modelo de machine learning, você pode seguir os passos abaixo (não inclusos no código original, mas aqui está um exemplo simples usando regressão linear):

python
Copiar código
import pandas as pd
from sklearn.linear_model import LinearRegression
import pickle

# Carregar os dados (supondo um arquivo CSV com colunas 'm2' e 'valor')
dados = pd.read_csv('imoveis.csv')

# Treinamento do modelo
X = dados[['m2']]  # Características
y = dados['valor']  # Rótulos (preço)

modelo = LinearRegression()
modelo.fit(X, y)

# Salvar o modelo treinado
with open('modelo_treinado.pkl', 'wb') as file:
    pickle.dump(modelo, file)
Contribuições
Sinta-se à vontade para contribuir para este projeto. Caso tenha sugestões ou correções, envie um pull request ou abra uma issue.

Licença
Este projeto está licenciado sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

markdown
Copiar código

### Notas:

- O código foi estruturado para garantir que a previsão de valores seja feita de maneira simples e interativa usando o Streamlit.
- O modelo de machine learning deve ser treinado e salvo em um arquivo `.pkl` para que o código funcione corretamente.
