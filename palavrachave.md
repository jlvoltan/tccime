# :memo: Palavras-chave

:speech_balloon: Aqui iremos alterar o separador das palavras-chave, originalmente se utilizava o ponto final (.), entretando, tem-se solicitado o uso da vírgula (,), exceto para a última..

:one: Ir no arquivo *abntex2ime.sty*

:two: Comentar essa parte (inserção do %):

<pre>
% \providecommand{\imprimirpalavraschave}{}
% \providecommand{\imprimirpalavraschavefichacatalografica}{}
% \newcommand{\palavraschave}[1]{
% \readlist*\mylistpalavraschave{#1}
% \renewcommand{\imprimirpalavraschave}{\foreachitem\x\in\mylistpalavraschave[]{\x.\ifx\xcnt\mylistpalavraschavelen\else \ \fi}}
% \renewcommand{\imprimirpalavraschavefichacatalografica}{\foreachitem\x\in\mylistpalavraschave[]{\xcnt . \x . }}
% }
</pre>

:three: Adiciona o trecho de código a seguir, logo a baixo do que ficou comentado: 

<pre>
\providecommand{\imprimirpalavraschave}{}
\providecommand{\imprimirpalavraschavefichacatalografica}{}
\newcommand{\palavraschave}[1]{
  \readlist*\mylistpalavraschave{#1}
  \renewcommand{\imprimirpalavraschave}{\foreachitem\x\in\mylistpalavraschave[]{\x\ifnum\xcnt=\mylistpalavraschavelen.\else; \fi}}
  \renewcommand{\imprimirpalavraschavefichacatalografica}{\foreachitem\x\in\mylistpalavraschave[]{\xcnt . \x \ifnum\xcnt=\mylistpalavraschavelen.\else; \fi}}
}
</pre>

:four: Replicar para o inglês:

- Comentar:
<pre>
% Keywords
% \providecommand{\imprimirkeywords}{}
% \newcommand{\keywords}[1]{
% \readlist*\mylistkeywords{#1}
% \renewcommand{\imprimirkeywords}{\foreachitem\x\in\mylistkeywords[]{\x.\ifx\xcnt\mylistkeywordslen\else \ \fi}}
% }
</pre>

- Inserir:

<pre>
\providecommand{\imprimirkeywords}{}
\newcommand{\keywords}[1]{
  \readlist*\mylistkeywords{#1}
  \renewcommand{\imprimirkeywords}{\foreachitem\x\in\mylistkeywords[]{\x\ifnum\xcnt=\mylistkeywordslen.\else; \fi}}
}
</pre>
