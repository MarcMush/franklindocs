@def author = "Thibaut Lienart"
@def hasmath = false              <!-- mostly there's no maths on pages -->
@def generate_rss = false

@def prepath = "franklindocs"     <!-- it's a GitHub project website -->

@def mintoclevel = 2              <!-- TOCS only for level h2 and higher -->
@def maxtoclevel = 3              <!-- TOCS only up to level 3 included -->

@def hasplotly = false

@def folder_structure = v"0.1"

<!--
Useful HTML snippets
* \blurb{...} for a blurb at the top of a page
* \refblank{...} for a link with target blank
* \lineskip forces skipping of a line somewhere
-->

\newcommand{\blurb}[1]{
    ~~~
    <span style="font-size:24px;font-weight:300;">!#1</span>
    ~~~
}
\newcommand{\refblank}[2]{
    ~~~
    <a href="!#2" target="_blank" rel="noopener noreferrer">#1</a>
    ~~~
}
\newcommand{\lineskip}{@@blank@@}
\newcommand{\skipline}{\lineskip}
\newcommand{\note}[1]{@@note @@title ⚠ Note@@ @@content #1 @@ @@}

\newcommand{\esc}[2]{
    ```julia:esc__!#1
    #hideall
    using Markdown
    println("\`\`\`\`\`plaintext $(Markdown.htmlesc(raw"""#2""")) \`\`\`\`\`")
    ```
    \textoutput{esc__!#1}
}

\newcommand{\esch}[2]{
    ```julia:esc__!#1
    #hideall
    using Markdown
    println("\`\`\`\`\`html $(Markdown.htmlesc(raw"""#2""")) \`\`\`\`\`")
    ```
    \textoutput{esc__!#1}
}

\newcommand{\span}[2]{~~~<span style="display:inline-block;!#1">~~~!#2~~~</span>~~~}

\newcommand{\goto}[1]{~~~<a href="!#1" id="goto"><span id="check">&check;</span><span id="arrow"><b>&rarr;</b></span></a>~~~}