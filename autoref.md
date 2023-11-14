# :bookmark_tabs: Autoref
<div align="center"> 
<img src="/imagens/autoref.gif" alt="Descrição da imagem" width="300">
</div>

:speech_balloon: Aqui iremos alterar . Ao se referir a um Capítulo, Seção, Subseção específica, devemos utilizar a inicial maiúscula. Acontece que o comando `\autoref{}` está configurado para inserir essas palavras todas minúsculas .

:one: Ir no arquivo *abntex2.cls*

:two: Comentar essa parte (inserção do %):

<pre>
  % \renewcommand{\sectionautorefname}{se{\c c}\~ao}
  % \renewcommand{\subsectionautorefname}{subse{\c c}\~ao}
  % \renewcommand{\subsubsectionautorefname}{subse{\c c}\~ao}
  % \renewcommand{\paragraphautorefname}{subse{\c c}\~ao}
</pre>

:three: Adiciona o trecho de código a seguir, logo a baixo do que ficou comentado: 

<pre>
  \renewcommand{\sectionautorefname}{Se{\c c}\~ao}
  \renewcommand{\subsectionautorefname}{Subse{\c c}\~ao}
  \renewcommand{\subsubsectionautorefname}{Subse{\c c}\~ao}
  \renewcommand{\paragraphautorefname}{Subse{\c c}\~ao} 
</pre>
