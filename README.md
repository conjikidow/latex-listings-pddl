# pddl-latex-listings
A syntax highlighting support for PDDL in the LaTeX listings package.

## How to Set Up
1. Create `lstlang0.sty` in your texmf trees (if it does not already exist).
    - You can use either of `TEXMFLOCAL` or `TEXMFHOME` as texmf trees.
        - To see the values of these variables, run `tlmgr conf`.
    - Put `lstlang0.sty` in `texmf_tree_root/tex/latex/listings/`.
        - Like, `${TEXMFHOME}/tex/latex/listings/lstlang0.sty`.
2. Clone this repository.
    - Clone it into the same directory with `lstlang0.sty` (`texmf_tree_root/tex/latex/listings/`).
3. Include the [`lstlang-pddl.sty`](lstlang-pddl.sty) in the `lstlang0.sty`.
    - Add
        ```latex
        \input{pddl-latex-listings/lstlang-pddl.sty}
        ```
        in the `lstlang0.sty`.

## How to Use
- Set the option `language` as `PDDL` in the lstlisting environment.
    - Example:
        ```latex
        \begin{lstlisting}[language=PDDL]
        (define (domain example)
            ...
        )
        \end{lstlisting}
        ```
- You can specify a specific version of PDDL.
    - Example:
        ```latex
        \begin{lstlisting}[language={[1.2]PDDL}]
        (define (domain example)
            ...
        )
        \end{lstlisting}
        ```
    - Available versions:
        - 1.2
            - Note that some features of PDDL1.2 are not supported, since they are rarely used.
        - 2.1
        - 2.2
        - 3.0
        - 3.1
            - This is set as the default.
    - To change the default version, set the `defaultdialect` like
        ```latex
        \lstset{defaultdialect=[2.1]PDDL}
        ```
- You can also include PDDL source files in a similar manner.
    - Example:
        ```latex
        \lstinputlisting[language={[2.2]PDDL}]{path/to/source/domain.pddl}
        ```
- See more for the listing package [here](https://ctan.org/pkg/listings).

## References
- McDermott, D., Ghallab, M., Howe, A., Knoblock, C., Ram, A., Veloso, M., Weld, D., and Wilkins, D. (1998). PDDL - The Planning Domain Definition Language. https://www.researchgate.net/publication/2278933_PDDL_-_The_Planning_Domain_Definition_Language
- Fox, M. and Long, D. (2003). PDDL2.1: An Extension to PDDL for Expressing Temporal Planning Domains. _Journal of Artificial Intelligence Research_, 20, 61–124. https://doi.org/10.1613/jair.1129
- Edelkamp, S. and Hoffmann, J. (2004). PDDL2.2: The Language for the Classical Part of the 4th International Planning Competition. University of Freiburg. Baden-Württemberg, Germany. https://courses.cs.washington.edu/courses/cse473/06sp/pddl2.2.pdf
- Gerevini, A. and Long, D. (2005). BNF Description of PDDL3.0. https://ipc06.icaps-conference.org/deterministic/bnf.pdf
- Kovacs, D. L. (2011). Complete BNF description of PDDL3.1. http://www.plg.inf.uc3m.es/ipc2011-deterministic/attachments/Resources/kovacs-pddl-3.1-2011.pdf
- Helmert, M., and Haslum, P. (2011). Changes in PDDL 3.1. IPC-2008, Deterministic Part. https://ipc08.icaps-conference.org/deterministic/PddlExtension.html