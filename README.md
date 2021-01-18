# Latex template for CS207

## Steps

1. Copy paste questions from pdf to .tex file
    1. convert pdf to text by pdftotext command in terminal(install by `pip install pdftotext` ). Command `pdftotext ques.pdf ques.txt` to convert pdf to text.
    2. directly copy paste from pdf.
 
2. Paste questions in .tex file between begin{enumerate} and end{enumerate}

3. Using regex to quickly modify file
    1. vscode
        1. **to convert explicit numbering to \item{} inside enumeration use**
        
            string_to_search = `^\d+\.\s(.*)$`
            
            string_to_replace =  `\hrule\n\\item{$1}\n`

        2. **to remove page numbers**   
             string_to_search = `^Page\s\d+$`
             
             string_to_replace = empty


    2. vim
        1. **to convert explicit numbering to \item{} inside enumeration use**
            `:%s/^\d\+\.\s\(.*\)$/\\hrule\r\\item{\1}\r`
        2. **to remove page numbers**
            `:%s/^Page\s\d\+$/`
        3. **Change vim settings to add shortcut to compile the file**
            `map ,l :! pdflatex %<CR><CR>` // this will create shortcut comma+l to compile the latex document from vim itself. if file has few small bugs then will need to press enter/return key certain times. if no error then this would work fine

