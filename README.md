# Análise da Participação por Gênero no Issue Tracking do Github

<img hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/gif.gif">

Esse projeto foi desenvolvido durante meu trabalho de conclusão de curso. Neste repositório estão armazenados os dados que realizei a extração, e tratamento, de forma que pudesse ser feita a análise sobre a qualidade e quantidade da participação de homens em mulheres em issues da plataforma do GitHub.



<br>

### **☕️ Extração e Tratamento dos Dados**

Como primeira etapa do trabalho foi realizado a seleção dos repositórios a serem extraídos pelo trabalho, para isso foram selecionados repositórios de projetos open source na plataforma do GitHub que possuissem alguma correspondência de temas com projetos open source que trabalham para realizar a inclusão e permanência de mulheres na área da computação. Abaixo estão listados os projetos utilizados então na extração dos dados.


Após extraídos os dados, foi realizado o cálculo da relevância temática de cada um dos comentários das issues, em que a métrica da relevância temática é calculada utilizando do conceito da similaridade de cossenos, que realiza a verificação da similaridade de um comentário com a sua issue em questão, sendo expressado pela fórmula:

$RT = \frac{S_{CI} + S_{CD}}{2}$

em que, ($S_{CI}$) é a similaridade do comentário em relação à issue, considerando seu título e descrição, e ($S_{CD}$) sendo a similaridade do comentário com a discussão, que considerada além da issue os comentários anteriores.

Por fim, durante a extração e tratamento dos dados foi feito a verificação do gênero de cada uma das pessoas desenvolvedoras participantes das issues, tanto em comentários, quanto na postagem de issues, utilizando da ferramenta [NamSor](https://namsor.app/), que ao enviar o nome da pessoa desenvolvedora ele retorna o gênero ao qual o mesmo possui maior propabilidade de ser, dessa forma, como é utilizado apenas do nome, os gêneros possíveis são feminino e masculino. Além disso, também é calculado a reputação do desenvolvedor, que leva em consideração o cálculo feito pela plataforma do [GitScore](http://www.gitscore.com/).

<br>

### **🎲 Sobre os Dados**

Para auxiliar no processo de análises futuras dos dados aqui armazenados, abaixo é deixado uma tabela com a descrição de cada uma colunas dos dois datasets gerados durante a extração dos dados. Primeiramente temos as informações sobre os dados de comentários das issues, em que é importante ressaltar que todas as colunas que possuem o nome issue inclusa possuem informações extraídas pela API do GitHub, ou seja, questões como o título e descrição da issue.

NumeroComentario | Comentario | DataComentario | RelevanciaTematica | Reputacao | AnosPlataforma | Genero
:------: | :------: | :------: | :------: | :------: | :------: | :------: |
Inteiro, indicando o número do comentário na issue | String, contendo o conteúdo do comentário | Date, contendo a data de postagem do comentário | Float, valor calculado da relevância temática do comentário | Int, valor calculado da reputação da pessoa desenvolvedora que realizou a postagem do comentário | Int, número de anos de participação da pessoa desenvolvedora que realizou a postagem do comentário | String, gênero da pessoa desenvolvedora que realizou a postagem do comentário

E segundamente, e finalmente, as informações sobre os dados das issues em si.

NumeroIssue | Genero
:------: | :------: | 
Int, contendo o número da issue em questão | Strig, contendo o gênero da pessoa desenvolvedora que criou a issue em questão

<br>

### **📊 Análise dos Dados**

Para a análise dos dados foi utilizado do Jupyter Notebook, gerando assim diversos gráficos com informações relevantes sobre os dados extraídos. Tais análises levaram em consideração os tópicos levantados durante a escrita do artigo para defesa do trabalho de conclusão de curso, sendo os pontos mais importantes entender a diferença na qualidade dos comentários feitos por homens e mulheres, a quantidade de comentários e issues postados por homens e mulheres, e a relação da métrica de relevância temática dos comentários em relação aos anos de participação das pessoas desenvolvedoras na plataforma do GitHub e a reputação das mesmas.

<br>

### **⭐️ Resultados**

Os resultados obtidos durante as análises dos dados até o momento foram publicados nos [anais]() do curso de Ciência da Computação da UFV/Florestal, e no Women in Technology ([WiT](https://sol.sbc.org.br/index.php/wit/article/view/20873)) em formato de artigo resumido. Além disso, o trabalho recebeu o 🥇 prêmio de melhor artigo resumido no WiT na edição de 2022!