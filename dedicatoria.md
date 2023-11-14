# :memo: Dedicatória

<h1 align="center">
    <img src="/imagens/dedicatoria.gif">
</h1>


:speech_balloon: Aqui iremos alterar o alinhamento da dedicatória, deixando-a alinhada na parte inferior direita.

:one: Ir no arquivo *pre-texto.tex*

:two: Comentar essa parte (inserção do %):

<pre>
% Dedicatória
% ---
% \begin{dedicatoria}
%    \vspace*{\fill}
%    \centering
%    \noindent
%    \textit{Ao meu pai, pelo seu exemplo 
%    de dedicação e abnegação.} \vspace*{\fill}
% \end{dedicatoria}
</pre>

:three: Adiciona o trecho de código a seguir, logo a baixo do que ficou comentado: 

<pre>
\begin{dedicatoria}
    \vspace*{\fill}
    \begin{flushright}
        \begin{minipage}[b][3cm][b]{0.7\textwidth}
       \textit{Ao meu pai, José Luiz Voltan (In Memoriam), pelo seu exemplo de dedicação e abnegação.}
        \end{minipage}
    \end{flushright}
\end{dedicatoria}
</pre>
