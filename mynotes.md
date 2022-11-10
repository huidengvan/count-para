

pandoc 1.md --to pdf --toc --toc-depth=6  --output 1.pdf  --lua-filter C:\git-repos\count-para\count-para.lua --pdf-engine=xelatex

pandoc 1.md --to pdf --toc --toc-depth=6  --output 1.pdf  -V CJKmainfont="KaiTi" --pdf-engine=xelatex 

pandoc 1.md --to pdf --toc --toc-depth=6  --output 1.pdf  -V CJKmainfont="KaiTi" --pdf-engine=xelatex --lua-filter C:\git-repos\count-para\count-para.lua

pandoc 1.md --to html --toc --toc-depth=6  --output 1.html  -V CJKmainfont="KaiTi" --lua-filter C:\git-repos\count-para\count-para.lua

## generate word docx file with toc and auto numbered header

pandoc test.md --to docx --toc --toc-depth=6 --output test.docx -V 'mainfont:DejaVu Sans' -V 'CJKmainfont:Yuanti SC' -N -Vsecnumdepth=6 -H options.sty -V CJKmainfont="KaiTi" --pdf-engine=xelatex --lua-filter C:\git-repos\count-para\count-para.lua


echo "--- `date` $1 ---"
pandoc $1 -f markdown -s \
    -V 'mainfont:DejaVu Sans' \
    -V 'CJKmainfont:Yuanti SC' \
    --pdf-engine=xelatex --toc --number-section  \
    -H $(dirname $0)/options.sty \
    -o $1.pdf

echo "--- `date` $1 done. ---" 
echo ""

Get-ChildItem –Path "." -Recurse -Filter *.md | Foreach-Object {
echo $_.FullName $_.FullName.replace(".md",".docx")
pandoc $_.FullName --to docx --toc --toc-depth=6 --output $_.FullName.replace(".md",".docx") -V 'mainfont:DejaVu Sans'  -N -Vsecnumdepth=6 -V CJKmainfont="KaiTi" --lua-filter C:\git-repos\count-para\count-para.lua
}