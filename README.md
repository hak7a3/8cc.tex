# 8cc.tex

This is a TeX source of [8cc](https://github.com/rui314/8cc) built on [ELVM](https://github.com/shinh/elvm).
In other words, this is a complete C compiler written in TeX.

This is very influenced by [8cc.vim](https://github.com/rhysd/8cc.vim).

# Usage



```bash
printf \\000 | cat sample/hello.c - | od -A n -t d1 -w1 -v | tex 8cc.tex # compile C code to ELVM IR.
echo 0 | cat 8cc.tex.elvm.out - | tex elc.tex
cat elc.tex.elvm.out | xargs printf "%03o\n" | xargs -I_ printf \\_ > hello.tex # compile ELVM IR to TeX source.
tex hello.tex # execute
cat hello.tex.elvm.out | xargs printf "%03o\n" | xargs -I_ printf # show stdout
```