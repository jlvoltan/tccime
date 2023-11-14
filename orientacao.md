# :on: Orientação página

<div align="center"> 
<img src="/imagens/deitado.gif" alt="Descrição da imagem" width="300">
</div>



:speech_balloon: Aqui iremos alterar a orientação de uma página específica. Isso pode ser útil por exemplo em uma página onde existe uma tabela.

:one: Ir no arquivo *main.tex* e adicionar o pacote _pdflscape_

<pre>
\usepackage{pdflscape}
</pre>


:two: Ir no arquivo *.tex* onde está a página que deseja-se alterar. Inserir o conteúdo da página dentro do ambiente landscape:

<pre>
\begin{landscape}

  % Seu conteúdo

\end{landscape}

</pre>
