# Haskell and Dockerize your tools container pattern

In this repository we share an example of "Haskell and Dockerize your tools container pattern" for the workshop [5 containers patterns for 5 languages](https://l0rd.github.io/talks/containers-and-languages/index_en.html).

Haskell Game Of Life source code can be found at [rosettacode.org](https://rosettacode.org/wiki/Conway%27s_Game_of_Life#Haskell) 

The [Haskell Scotty todolist](https://github.com/jhedev/todobackend-haskell/tree/master/todobackend-scotty) has been developed by [jhedev](https://github.com/jhedev/) as a sample web application for [Scotty](https://hackage.haskell.org/package/scotty). Scotty is a framework to write RESTful, declarative web applications.


```bash
git clone https://github.com/containerslanguages/haskell
alias ghc="docker run --rm -t -v $(pwd):/src/ -w /src/ haskell:8.0 ghc"
alias stack="docker run --rm -it -v ~/.stack:/root/.stack -v $(pwd):/code -w /code haskell:8.0 stack"

ghc gameoflive/gol.hs
docker run -v $(pwd)/gameoflife/gol:/app/gol haskell:8.0 /app/gol

cd todobackend
stack build todobackend-scotty
stack exec todobackend-scotty

#alias stack="docker run --rm -it -v ~/.stack:/root/.stack -v $(pwd):/code -w /code haskell:8.0 bash -c 'stack build todobackend-scotty --allow-different-user'"
```
