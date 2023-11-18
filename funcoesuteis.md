

## Pacote ulem:  
- Este pacote oferece vários tipos de decoração de texto, incluindo sublinhado, itálico, negrito e riscado.

  
- Importar o pacote na main.tex
`\usepackage[normalem]{ulem}`

- No texto, para deixa o conteúdo tachado, representando p.e. uma sugestão de exclusão: `\sout{ }`  


## Comentarios Orientador e Orientado:

- Duas sugestões com estilos diferentes:

#### Opção 1:
- Importar o pacote na main.tex

<pre>
\usepackage{todonotes}
\newcommand\ronaldo[1]{\todo[inline, color=red]{\textbf{Ronaldo}: #1}}
\newcommand\voltan[1]{\todo[inline, color=blue]{\textbf{Voltan}: #1}}
</pre>

#### Opção 2 
- Importar o pacote na main.tex
<pre>
\usepackage{color}
\newcommand\ronaldo[1]{\textcolor{blue}{#1}}
\newcommand\voltan[1]{\textcolor{red}{#1}}'''
</pre>

- Para utilizar no texto, basta colocar p.e. \voltan{O que estiver aqui dentro ficará na cor vermelha.}
