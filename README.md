# Data Challenge Stone

![image](https://user-images.githubusercontent.com/77629603/167406439-8eab1481-0d6c-45fd-b777-9b6a8a9b30a0.png)


# 1. Contexto

O contexto do problema foi um desafio de dados lançado pela Stone.

# 2. Desafio

O desafio foi analisar dados de 14,7 mil clientes que participaram de um programa de empréstimos, onde pagariam através da retenção de um percentual do pagamento na maquininha da Stone. Porém, muitos desses clientes estão com pagamento atrasado. O objetivo principal da análise vai ser medir a eficiência dos acionamentos aos clientes e a pergunta chave é: Qual a curva ideal de vezes que devemos acionar um cliente?

## 2.1. Premissas 
* Os dados são de dez-2019 até abr-2022. 
* Os registros após quitação do contrato foram removidos, pois esses registros não têm importância dado o problema.
* Somente comunicados lidos e respondidos foram considerados para medir eficiência média.
* Valores negativos de preço e quantidade foram removidos.


# 3. Solução

## 3.1. Limpeza

Nessa etape houve a filtragem de linhas e colunas que não eram considerados importantes para o problema, diminuindo a demanda de processamento e o tamanho dos arquivos. Alguns dados estranhos foram removidos para não haver problemas nas análises.

## 3.2. Modelagem

Nesta etapa foram feitos os joins de tabelas e a divisão dos mesmos para construir os relacionamentos. Além disso, novas features foram criadas, com o destaque da feature "eficiência" que media a eficiência de cada ação. A eficiência tinha valor 1 se o pagamento fosse retomado, valor 2 se o pagamento principal fosse retornado e 0 se o paagamento não fosse retornado, isso tudo se o comunicado foi lido e para os 5 dias seguintes.

## 3.3. Dashboard Power BI

Nesta etapa finalmente começei a criar o dashboard no Power BI. 
* A primeira página tinha o objetivo de mostrar os resultados do programa de empréstimos ao longo dos anos, focando nos resultados esperados vs realizados.
* A segunda página mostra a eficiência das ações ao longo do tempo. (Nesta página os dados são resumidos em médias, tentando generalizar o comportamento dos dados).
* A terceira página é semelhante a segunda, porém utilizei um filtro por contrato dinâmico, onde é possível observar individualmente como cada contratante se comportou com as ações.

[Link](https://app.powerbi.com/view?r=eyJrIjoiZjg1MTBiNTMtYTU1ZC00Yjc4LTgwYjctODE1OTVlNDFhMDlhIiwidCI6Ijg3MDk0MzhmLTMzNDItNGI0Yy1hZDY5LTNkMjFlMmY4OTZlOSJ9) Para acessar o dashboard 

## 3.4. Análise Python

Nesta etapa foram feitas algumas análises complementares para validar algumas conclusões.

## 3.5. Insights

Finalizei o projeto resumindo os principais insights provenientes das análises.

### 3.5.1 Principais Insights

1. O comportamento médio geral da eficiência e os dias sem pagar são muito variáveis;
2. A eficiência média das ações tendem a cair bastante a medida que o contrato se prolonga;
3. O comportamento em relação ao tipo de ação, e a eficiência das ações ao longo do tempo sem pagar é muito variável. Não é possível perceber uma grande linearidade de comportamento. Mas com certeza é possível aferir que o melhor intervalo de acionamento até o dia 10 sem pagamento, depois disso o comportamento varia muito.]
4. Taxa de leitura das ações: 35.09%;
5. Taxa de eficiência das ações lidas: 42.16% ;
6. No script é possível observar o impacto que teria caso mais mensagens
fossem entregues;
7. A campanha de Pré Negativação é mais eficiente que a campanha de Boleto
Quitado, mesmo sendo uma campanha mais tardia.

### 3.5.2 Conclusão

A eficiência das ações variam muito em cada situação, não é possível fazer uma generalização. Mas é certo que elas perdem eficiência ao longo do tempo então o melhor momento para focar nas ações é nos primeiros dias de atraso no pagamento. 

# 4. Downloads e Referências

## 4.1. Downloads 
[Link](https://drive.google.com/drive/folders/1eyOZw57JCNPVBEO1UdIR57TSO6L71qVq?usp=sharing) para drive com arquivos que aqui estão como LSF

## 4.2. Referências

* [Desafio Stone](https://sites.google.com/stone.com.br/stonetech/desafio?authuser=0mOKSe0Oi6rK/view?usp=sharing&utm_source=Top+Minds+Challenge+Stone&utm_campaign=45cab5370e-EMAIL_CAMPAIGN_2022_04_27_05_51&utm_medium=email&utm_term=0_cb8116f6f4-45cab5370e-65361127)
* [Play axis Power BI](https://www.youtube.com/watch?v=2G_fOhbvQe8&pp=ugMICgJwdBABGAE%3D)
* [Como enviar arquivos grandes no GitHub](https://www.youtube.com/watch?v=uLR1RNqJ1Mw)
