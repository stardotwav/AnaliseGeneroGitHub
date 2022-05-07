# Trabalho de Conclusão de Curso

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/ola.gif">

**Tema:** Relevância Temática dos Comentários e Diversidade de Gênero em Projetos Open Source

**Autora:** Estela Miranda Batista

**Orientadora:** Gláucia Braga

**Resumo:** Este trabalho analisa a participação feminina em termos da relevância temática dos comentários postados no ambiente de issue tracking do GitHub. O trabalho também investiga possíveis relações entre a relevância temática e outras métricas ligadas ao desenvolvedor, como reputação, tempo de plataforma e número de issues reportadas. Foram analisados dados de 5 comunidades open source abertas, e 5 dedicadas às mulheres. Os resultados apontam que, na média, a relevância dos comentários feitos por mulheres é similar à dos homens, se mostrando igualmente capazes, porém demonstram uma representatividade e participação muito baixas, tendo apenas
22% dos comentários postados e 16% das issues reportadas.

**Áreas de Conhecimento:** Ciência dos Dados e Engenharia de Software

<br>

### 🔴 Extração dos Dados
Para realizar a extração dos dados foi utilizado da [Biblioteca ColMiner RT](), que foi desenvolvida no contexto da minha iniciação científica, no NuPESSC. A biblioteca tem como objetivo extrair informações das comunicações de issue tracking da plataforma do GitHub, de forma que cada comentário ao ser analisado e seja atribuída uma relevância temática para o mesmo. O cálculo da relevância dos comentários leva em comparação a similaridade do comentário com a issue, sendo considerado o título e a descrição das mesma ($S_{CI}$), e a similaridade do comentário com a discussão, sendo a discussão dada pela união entre a issue e o comentário anterior ao analisado ($S_{CD}$), sendo isso expressado na equação abaixo.

$RT = \frac{S_{CI} + S_{CD}}{2}$

Depois de calculado relevância temática de todos os comentários de todas as issues de um determinado repositório da plataforma do GitHub os dados são salvos em um arquivo .csv. É importante citar para as análises realizadas nesse trabalho foram usados apenas de issues fechadas, para evitar que os dados necessitassem ser atualizados ao longo da pesquisa.

<br>

### 🟠 Pré-Processamento dos Dados
Após extraídos os dados, pensando agora nas questões de gênero do trabalho, temos que foi necessário identificar o gênero de cada um dos desenvolvedores envolvidos, em que para isso foi utilizado da ferramenta [NamSor](). O gênero dos desenvolvedores levou em consideração tanto os autores das issues, quanto os autores de comentários.

Além disso, pensando em análises sobre o comportamento em diferentes tipos de ambientes, diversos e não diversos, foi contabilizado o número de mulheres e homens em cada comunidade que se teve repositórios extraídos. Com essa informação então foi possível realizar o cálculo do Índice Blau, que nos indica o nível de diversidade em cada comunidade, sendo que 0 indica a falta de diversidade, e 0.5 que o time está com o mesmo número de homens e mulheres, ou seja, muito diverso. O Índice Blau é dado pela equação apresentada abaixo.

$Blau = 1 - \sum^{N}_{i=1} P^{2}_{i}$

Por fim, como parte do pré-processamento dos dados, foi necessário também para responder às questões de pesquisa saber a reputação dos desenvolvedores que responderam à comentários no issue tracking, e visto que a plataforma do GitHub não realiza o cálculo dessa informação, foi utilizado da plataforma do [GitScore]() para calcular o mesmo.

<br>

### 🟡 Análise dos Dados
Para começar a apresentar os dados, primeiramente iremos olhar para as comunidades extraídas, em que 5 delas são comunidades dedicadas às mulheres, sendo as 5 primeiras mostradas nas imagens, e as outras 5 comunidades são abertas. Ao analisarmos a imagem do gráfico com a imagem da tabela, é possível notar que comunidades como RailsGirls são muito diversas, mas sua comunidade similar aberta, sendo a RubyonRails, possuem uma diversidade baixa, sendo que ao analisar as comunidades foi possível notar que a maioria das mulheres presentes na comunidade RubyonRails também está presente na comunidade RailsGirls.

<br>

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/tabelaDadosComunidades.png">

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/mulheresHomensIndiceBlau.png">

<br>

Além disso, foram então respondidas algumas questões de pesquisa, que serão apresentadas agora de forma resumida. Para acessar as informações completas de cada questão de pesquisa, basta acessar o meu artigo publicado nos anais do meu curso [Artigo]().

<br>

**🟢 1. Qual a diferença de participação de homens e mulheres em termos de issues e comentários associados?**

Para essa questão de pesquisa, como apresentado no gráfico, foi levandado que das 1275 issues extraídas, 1071 (84%) foram reportadas por homens, e 204 (16%) por mulheres. Além disso, temos que dos 9151 comentários extraídos, 6897 (88%) foram postados por homens, e 2059 (22%) por mulheres.

<br>

<img hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/issuesComentarios.png">

<br>

**🔵 2. Existe diferença entre a relevância dos comentários postados por homens e mulheres?**

Ao analisarmos a base de dados, e utilizarmos de uma média, foi possível notar que a média de homens e mulheres tem uma diferença quase nula, em que os homens tem uma média de 0.03680, e as mulheres tem uma média de 0.03394, sendo então observado uma diferença entre ambos no intervalo das relevâncias, em que as mulheres possuem um intervalo menor, como apresentado nas imagens.

<br>

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/comunidadesAbertas.png">

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/comunidadesExclusivas.png">

<br>

**🟣 3. Existe relação entre a relevância dos comentários e a reputação do autor?**

Ao analisar os dados extraídos, foi possivel notar que a relevância temática dos comentários, e a reputação dos autores não tinha relação, isso porque como podemos ver nas imagens, o intervalo de dados das reputações variam com todos os valores de relevância temática. Uma observação interessante que foi possivel ser realizada é a de que o intervalo de reputação das mulheres é menor que a de homens, tendo elas a sua concentração maior na faixa de $10^{3}$.

<br>

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/relevanciaTematicaReputacaoHomens.png">

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/relevanciaTematicaReputacaoMulheres.png">

<br>

**⚪️ 4. Existe relação entre a relevância dos comentários e o tempo de participação na plataforma?**

Por fim, temos que o tempo de participação na plataforma também não está relacionado com a relevância temática, isso porque como mostrado nas imagens, temos que em todos os anos, obtivemos uma variação similar nos valores de relevância dos comentários. Sendo importante citar que as mulheres tem um tempo de permanência menor, em que elas se concentram em cerca de 4 a 10 anos, enquanto os homens tem uma grande presença até os 14 anos de participação.

<br>

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/relevanciaTematicaAnosPlataformaHomens.png">

<img align="left" hspace="50" vspace="50" height="200" src="https://github.com/stardotwav/AnaliseGeneroGitHub/blob/main/Imagens/relevanciaTematicaAnosPlataformaMulheres.png">
