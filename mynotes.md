

pandoc 1.md --to pdf --toc --toc-depth=6  --output 1.pdf  --lua-filter C:\git-repos\count-para\count-para.lua --pdf-engine=xelatex

pandoc 1.md --to pdf --toc --toc-depth=6  --output 1.pdf  -V CJKmainfont="KaiTi" --pdf-engine=xelatex 

pandoc 1.md --to pdf --toc --toc-depth=6  --output 1.pdf  -V CJKmainfont="KaiTi" --pdf-engine=xelatex --lua-filter C:\git-repos\count-para\count-para.lua

pandoc 1.md --to html --toc --toc-depth=6  --output 1.html  -V CJKmainfont="KaiTi" --lua-filter C:\git-repos\count-para\count-para.lua

## generate word docx file with toc and auto numbered header

pandoc test.md --to docx --toc --toc-depth=6 --output test.docx -N -Vsecnumdepth=6 -V CJKmainfont="KaiTi" --pdf-engine=xelatex --lua-filter C:\git-repos\count-para\count-para.lua
