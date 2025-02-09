# simplebook_markdown

Simple markdown for converting txt to html. Convertor included. 

Written in Python.

#2025-02-09-2

## What is it

It is a simple markdown convertor, made for converting scanned/written text to ebooks.

Each paragraph is separated by an empty line.

It will convert small set of markdown tags to html, with minimal modifications of the original text.

After that you can use pandoc/kindlegen[1]/calibre to convert it to the ebook (epub/mobi), or some other format.

.f1 Kindlegen can be found in the Kindle previewer package, unzip the installation and look for kindlegen.exe

## Reason

1. If you do not like it, then it's not for you. It is not made for programming, or math books.

It exists to solve two problems:

- not honoring newlines
- accidental rendering of text as tags. (1-2 3-4, rendered as text with a line through it.)

Or if you have a scanned book(s) you wish to convert to ebook(s), to read on your kindle.

To add more tags (tables, bold, italic, lists, code ...) use html code.

Or add custom tags in .py file.

## Installing

Download zip file (right click, save link as), unpack.

To convert txt to html, drag and drop your .txt file on .bat file.

You must have Python installed <a href="https://www.python.org/">https://www.python.org/</a>

## Tags supported

-Each part of text separated by empty lines will be added &lt;p> at the start of the block, and &lt;/p> at the end of the block, and be rendered as a paragraph.
To avoid this, add one space at the start of each line.

-New lines will be rendered as new lines. :)
It does not matter if text inside block is moved one space from the start, it will still be added new lines (&lt;br>)

Block tags:
-have to start at the start of the line, followed by space, and content:
-have to be preceded and followed by an empty line:
-<b>all text</b> will be surrounded by tag, <b>including</b> text after image.jpg, if there is any. You can add image description in the next line using ".pc description":
-If there is a line starting with space between two line, it will be joined in a single block, and will be rendered as such, with newline (&lt;br>) between lines.

-heading tags. Aligned center by default (using included css rules).

<table border=1>  <tr><td>.i flower.png</td>     <td>&lt;img src="flower.png"></td> </tr>  <tr><td>.1 This is heading size 1</td>     <td>&lt;h1 >This is heading size 1&lt;/h1></td> </tr>  <tr><td>.2 This is heading size 2</td>     <td>&lt;h2 >This is heading size 2&lt;/h2></td> </tr>  <tr><td>.3 This is heading size 3</td>     <td>&lt;h3 >This is heading size 3&lt;/h3></td> </tr>  <tr><td>.4 This is heading size 4</td>     <td>&lt;h4 >This is heading size 4&lt;/h4></td> </tr> </table>

.i flower.png

.1 This is heading size 1

.2 This is heading size 2

.3 This is heading size 3

.4 This is heading size 4


-text with
newline

<table border=1>  <tr><td>-text with<br>newline</td>     <td>&lt;p>-text with&lt;br>newline&lt;/p></td> </tr> </table>

-Footnotes[2]

<table border=1>  <tr><td>footnotes[2]</td>     <td>footnotes&lt;sup>&lt;a id="f2" href="#fb2">&#91;2]&lt;/a>&lt;/sup></td> </tr>   <tr><td>.f2 Footnotes are ...</td>     <td>   &lt;div id="fb2">&lt;a href="#f2">2.&lt;/a> Footnotes are ...&lt;/div>&lt;/a>    </td> </tr> </table>

it supports footnotes[2], footnotes will be moved to the end of the file, this can be changed.

.f2 Footnotes are ...

-Horizontal line, with space after .*

 <table border=1>  <tr><td>.* </td> <td>&lt;hr></td></tr></table>

.* 

-Table of contents (toc).
Make sure to add '.t ' (with space after t) at the location you want to place your toc.
Toc is created from headings (1-4) tags, with toc entry ID added automatically.


<table border=1>  <tr><td>.t </td>  <td> &lt;div>&lt;a href="#toc1">- simplebook_markdown&lt;/a>&lt;/div><br> &lt;div>&lt;a href="#toc2">- What is it&lt;/a>&lt;/div> <br> &lt;div>&lt;a href="#toc3">- Reason&lt;/a>&lt;/div> <br> &lt;div>&lt;a href="#toc4">- Tags supported&lt;/a>&lt;/div> <br> &lt;div>&lt;a href="#toc5">- This is heading size 1&lt;/a>&lt;/div> </td>  </tr> </table> 

.t 


## Custom block tags, enabled by default

Heading tags, which do the same as above, size 1-4:

<table border=1>  <tr><td># This is heading size 1</td> <td>&lt;h1 >This is heading size 1&lt;/h1></td> </tr>  <tr><td>## This is heading size 2</td> <td>&lt;h2 >This is heading size 2&lt;/h2></td> </tr>  <tr><td>### This is heading size 3</td> <td>&lt;h3 >This is heading size 3&lt;/h3></td> </tr>  <tr><td>#### This is heading size 4</td> <td>&lt;h4 >This is heading size 4&lt;/h4></td> </tr> </table>

# This is heading size 1

## This is heading size 2

### This is heading size 3

#### This is heading size 4

Paragraph texts are by default aligned justify, images center, headings left, but that can be changed by editing .py file in notepad++.

Custom paragraph text align center:

 <table border=1>  <tr><td>.pc Some text, centered horizontally</td> <td> &lt;p style="text-align:center !important;">Some text, centered horizontally&lt;/p></td></tr></table>

.pc Some text, centered horizontally

## Typing

&lt;p> will not be added to the text lines which start with space. Newline &lt;br> <b>will</b> be added.

If there are two lines separated with a line that contains only one space, all three lines will be joined into a paragraph. New line (&lt;br>) will be added after each line.

If you want to literally type html tags in text, like &lt;p>, you have to use &amp;lt;p> instead of &lt;p>. Single < is ok. More info here: <a href="https://www.w3schools.com/html/html_entities.asp">https://www.w3schools.com/html/html_entities.asp</a>

For left bracket, that is not part of the &#91;number] use &amp;#91; More info here: <a href="https://www.toptal.com/designers/htmlarrows/punctuation/left-bracket/">https://www.toptal.com/designers/htmlarrows/punctuation/left-bracket/</a>


## Parsing file name

By default parsing author - title.txt will parse as author and title. 

Author - series 3 - my title.txt, will also parse to 'author' and title: 'series 3 - my title'


## Conversion

To convert txt to html, drag and drop your .txt file on .bat file.

You can then convert .html to .mobi using kindlegen:
<code>
kindlegen.exe "Test Author - Series Name - 3 - Best Book.html" -dont_append_source -o "Test Author - Series Name - 3 - Best Book.mobi"
</code>

or use pandoc to convert .html to .epub:
<code>
pandoc.exe "Test Author - Series Name - 3 - Best Book.html" -s -o "Test Author - Series Name - 3 - Best Book.epub"
</code>

And then use kindlegen to convert .epub to .mobi:
<code>
kindlegen.exe "Test Author - Series Name - 3 - Best Book.epub" -dont_append_source -o "Test Author - Series Name - 3 - Best Book.mobi"
</code>

You can also use calibre:
<code>
ebook-convert.exe "Test Author - Series Name - 3 - Best Book.html" "Test Author - Series Name - 3 - Best Book.epub"
</code>
or
<code>
ebook-convert.exe "Test Author - Series Name - 3 - Best Book.epub" "Test Author - Series Name - 3 - Best Book.mobi"
</code>

## Html editors:

-1stPage2000 <a href="https://mega.nz/folder/xGESQQYL#rAlBgQ6QM-FJUhFdXW7Z5g">https://mega.nz/folder/xGESQQYL#rAlBgQ6QM-FJUhFdXW7Z5g</a>
-Seamonkey (Look in menu "windows/composer") <a href="https://www.seamonkey-project.org/">https://www.seamonkey-project.org/</a>

## Text editor:

-Notepad++ <a href="https://notepad-plus-plus.org/">https://notepad-plus-plus.org/</a>

