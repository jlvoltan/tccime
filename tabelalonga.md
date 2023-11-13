# :books: Tabelas e quadros longos

:speech_balloon: Aqui iremos configurar o _LATEX_ para aceitar quadros e tabelas com mais do que uma página .

:one: Ir no arquivo *main.tex*

:two: Inserir o seguinte trecho:

<pre>
% TESTE DO LONGO QUADRO  VOLTAN
\usepackage[strut=off]{caption}
\usepackage{float}
\usepackage{longtable}
\usepackage{xpatch}
\newfloat{quadro}{htbp}{loq}[chapter]
\floatname{quadro}{\quadroname}
\floatstyle{plaintop}
\restylefloat{quadro}

\makeatletter
% \renewcommand{\thequadro}{\thechapter.\@arabic\c@quadro}

% define env "longquadro"
\newenvironment{longquadro}
  {\patch@longtable
   \longtable}
  {\endlongtable}

% based on https://tex.stackexchange.com/a/548021
\@ifpackageloaded{caption}{
  \newcommand\patch@longtable{%
    \xpatchcmd\ltcaption@ORI@LT@array
      {\refstepcounter{table}}
      {\refstepcounter{quadro}}
      {}{\fail}%
    \renewcommand\LTcaptype{quadro}%
  }
}{
  \newcommand\patch@longtable{%
    \xpatchcmd\LT@array
      {\refstepcounter{table}}
      {\refstepcounter{quadro}}
      {}{}%
    % directly redefine "\LT@c@ption"
    \def\LT@c@ption##1[##2]##3{%
      \LT@makecaption##1\fnum@quadro{##3}%
      \def\@tempa{##2}%
      \ifx\@tempa\@empty\else
         {\let\\\space
         \addcontentsline{loq}{quadro}{\protect\numberline{\thequadro}{##2}}}%
      \fi}%
  }
}
\makeatother
</pre>

:three: Criar a tabela/quadro (a seguir um exmeplo ilustrativo): 

<pre>
% \begin{quadro}[htb]
\begin{center}
\begin{longquadro}{p{1cm}p{9cm}p{2cm}p{2cm}}
% \begin{tabular}{p{1cm}p{9cm}p{2cm}p{2cm}}
\caption{Referências dos documentos coletados.} \\
	\hline
	  ID & Título & Tipo & Rótulo \\ \hline 
        \endfirsthead
        \multicolumn{4}{c}%
        {\quadroname\ \thequadro\ -- \textit{Continuação do quadro}} \\
        \hline
        ID & Título & Tipo & Rótulo \\
        \hline
        \endhead
        \hline \multicolumn{4}{r}{\textit{Continua na próxima página}} \\
        \endfoot
        \hline \multicolumn{4}{r}{\textit{Fim do quadro}} \\
        \endlastfoot

        
1	&	Centro de Avaliações e Centro Tecnológico do Exército testam Míssil Anticarro	&	Notícia	&	Faixa 3	\\ \hline
%continua (...)  	

\end{longquadro}
\label{tab:datasetf}
\end{center}
</pre>
