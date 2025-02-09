 <h1 id="toc1">simplebook_markdown</h1>
<p>Simple markdown for converting txt to html. Convertor included. </p>
<p>Written in Python.</p>
<p>#2025-02-09-2</p>
 <h2 id="toc2">What is it</h2>
<p>It is a simple markdown convertor, made for converting scanned/written text to ebooks.</p>
<p>Each paragraph is separated by an empty line.</p>
<p>It will convert small set of markdown tags to html, with minimal modifications of the original text.</p>
<p>After that you can use pandoc/kindlegen<sup><a id="f1" href="#fb1">[1]</a></sup>/calibre to convert it to the ebook (epub/mobi), or some other format.</p>
 
 <h2 id="toc3">Reason</h2>
<p>1. If you do not like it, then it's not for you. It is not made for programming, or math books.</p>
<p>It exists to solve two problems:</p>
<p>- not honoring newlines<br>- accidental rendering of text as tags. (1-2 3-4, rendered as text with a line through it.)</p>
<p>Or if you have a scanned book(s) you wish to convert to ebook(s), to read on your kindle.</p>
<p>To add more tags (tables, bold, italic, lists, code ...) use html code.</p>
<p>Or add custom tags in .py file.</p>
 <h2 id="toc4">Installing</h2>
<p>Download <a href="https://github.com/dbojan/simplebook_markdown/raw/refs/heads/main/convert_simplebook_to_html.zip">zip file</a> (right click, save link as), unpack.</p>
<p>To convert txt to html, drag and drop your .txt file on .bat file.</p>
<p>You must have Python installed <a href="https://www.python.org/">https://www.python.org/</a></p>
 <h2 id="toc5">Tags supported</h2>
<p>-Each part of text separated by empty lines will be added &lt;p> at the start of the block, and &lt;/p> at the end of the block, and be rendered as a paragraph.<br>To avoid this, add one space at the start of each line.</p>
<p>-New lines will be rendered as new lines. :)<br>It does not matter if text inside block is moved one space from the start, it will still be added new lines (&lt;br>)</p>
<p>Block tags:<br>-have to start at the start of the line, followed by space, and content:<br>-have to be preceded and followed by an empty line:<br>-<b>all text</b> will be surrounded by tag, <b>including</b> text after image.jpg, if there is any. You can add image description in the next line using ".pc description":<br>-If there is a line starting with space between two line, it will be joined in a single block, and will be rendered as such, with newline (&lt;br>) between lines.</p>
<p>-heading tags. Aligned center by default (using included css rules).</p>
<p><table border=1>  <tr><td>.i flower.png</td>     <td>&lt;img src="flower.png"></td> </tr>  <tr><td>.1 This is heading size 1</td>     <td>&lt;h1 >This is heading size 1&lt;/h1></td> </tr>  <tr><td>.2 This is heading size 2</td>     <td>&lt;h2 >This is heading size 2&lt;/h2></td> </tr>  <tr><td>.3 This is heading size 3</td>     <td>&lt;h3 >This is heading size 3&lt;/h3></td> </tr>  <tr><td>.4 This is heading size 4</td>     <td>&lt;h4 >This is heading size 4&lt;/h4></td> </tr> </table></p>
 <img src="flower.png">
 <h1 id="toc6">This is heading size 1</h1>
 <h2 id="toc7">This is heading size 2</h2>
 <h3 id="toc8">This is heading size 3</h3>
 <h4 id="toc9">This is heading size 4</h4>
<p>-text with<br>newline</p>
<p><table border=1>  <tr><td>-text with<br>newline</td>     <td>&lt;p>-text with&lt;br>newline&lt;/p></td> </tr> </table></p>
<p>-Footnotes<sup><a id="f2" href="#fb2">[2]</a></sup></p>
<p><table border=1>  <tr><td>footnotes<sup><a id="f2" href="#fb2">[2]</a></sup></td>     <td>footnotes&lt;sup>&lt;a id="f2" href="#fb2">&#91;2]&lt;/a>&lt;/sup></td> </tr>   <tr><td>.f2 Footnotes are ...</td>     <td>   &lt;div id="fb2">&lt;a href="#f2">2.&lt;/a> Footnotes are ...&lt;/div>&lt;/a>    </td> </tr> </table></p>
<p>it supports footnotes<sup><a id="f2" href="#fb2">[2]</a></sup>, footnotes will be moved to the end of the file, this can be changed.</p>
 
<p>-Horizontal line, with space after .*</p>
 <table border=1>  <tr><td>.* </td> <td>&lt;hr></td></tr></table>
 <hr>
<p>-Table of contents (toc).<br>Make sure to add '.t ' (with space after t) at the location you want to place your toc.<br>Toc is created from headings (1-4) tags, with toc entry ID added automatically.</p>
<p><table border=1>  <tr><td>.t </td>  <td> &lt;div>&lt;a href="#toc1">- simplebook_markdown&lt;/a>&lt;/div><br> &lt;div>&lt;a href="#toc2">- What is it&lt;/a>&lt;/div> <br> &lt;div>&lt;a href="#toc3">- Reason&lt;/a>&lt;/div> <br> &lt;div>&lt;a href="#toc4">- Tags supported&lt;/a>&lt;/div> <br> &lt;div>&lt;a href="#toc5">- This is heading size 1&lt;/a>&lt;/div> </td>  </tr> </table> </p>
<p><div style="text-align:left !important"><a href="#toc1">- simplebook_markdown</a></div>
<div style="text-align:left !important"><a href="#toc2">- What is it</a></div>
<div style="text-align:left !important"><a href="#toc3">- Reason</a></div>
<div style="text-align:left !important"><a href="#toc4">- Installing</a></div>
<div style="text-align:left !important"><a href="#toc5">- Tags supported</a></div>
<div style="text-align:left !important"><a href="#toc6">- This is heading size 1</a></div>
<div style="text-align:left !important"><a href="#toc7">- This is heading size 2</a></div>
<div style="text-align:left !important"><a href="#toc8">- This is heading size 3</a></div>
<div style="text-align:left !important"><a href="#toc9">- This is heading size 4</a></div>
<div style="text-align:left !important"><a href="#toc10">- Custom block tags, enabled by default</a></div>
<div style="text-align:left !important"><a href="#toc11">- This is heading size 1</a></div>
<div style="text-align:left !important"><a href="#toc12">- This is heading size 2</a></div>
<div style="text-align:left !important"><a href="#toc13">- This is heading size 3</a></div>
<div style="text-align:left !important"><a href="#toc14">- This is heading size 4</a></div>
<div style="text-align:left !important"><a href="#toc15">- Typing</a></div>
<div style="text-align:left !important"><a href="#toc16">- Parsing file name</a></div>
<div style="text-align:left !important"><a href="#toc17">- Conversion</a></div>
<div style="text-align:left !important"><a href="#toc18">- Html editors:</a></div>
<div style="text-align:left !important"><a href="#toc19">- Text editor:</a></div></p>
 <h2 id="toc10">Custom block tags, enabled by default</h2>
<p>Heading tags, which do the same as above, size 1-4:</p>
<p><table border=1>  <tr><td># This is heading size 1</td> <td>&lt;h1 >This is heading size 1&lt;/h1></td> </tr>  <tr><td>## This is heading size 2</td> <td>&lt;h2 >This is heading size 2&lt;/h2></td> </tr>  <tr><td>### This is heading size 3</td> <td>&lt;h3 >This is heading size 3&lt;/h3></td> </tr>  <tr><td>#### This is heading size 4</td> <td>&lt;h4 >This is heading size 4&lt;/h4></td> </tr> </table></p>
 <h1 id="toc11">This is heading size 1</h1>
 <h2 id="toc12">This is heading size 2</h2>
 <h3 id="toc13">This is heading size 3</h3>
 <h4 id="toc14">This is heading size 4</h4>
<p>Paragraph texts are by default aligned justify, images center, headings left, but that can be changed by editing .py file in notepad++.</p>
<p>Custom paragraph text align center:</p>
 <table border=1>  <tr><td>.pc Some text, centered horizontally</td> <td> &lt;p style="text-align:center !important;">Some text, centered horizontally&lt;/p></td></tr></table>
 <p style="text-align:center !important;">Some text, centered horizontally</p>
 <h2 id="toc15">Typing</h2>
<p>&lt;p> will not be added to the text lines which start with space. Newline &lt;br> <b>will</b> be added.</p>
<p>If there are two lines separated with a line that contains only one space, all three lines will be joined into a paragraph. New line (&lt;br>) will be added after each line.</p>
<p>If you want to literally type html tags in text, like &lt;p>, you have to use &amp;lt;p> instead of &lt;p>. Single < is ok. More info here: <a href="https://www.w3schools.com/html/html_entities.asp">https://www.w3schools.com/html/html_entities.asp</a></p>
<p>For left bracket, that is not part of the &#91;number] use &amp;#91; More info here: <a href="https://www.toptal.com/designers/htmlarrows/punctuation/left-bracket/">https://www.toptal.com/designers/htmlarrows/punctuation/left-bracket/</a></p>
 <h2 id="toc16">Parsing file name</h2>
<p>By default parsing author - title.txt will parse as author and title. </p>
<p>Author - series 3 - my title.txt, will also parse to 'author' and title: 'series 3 - my title'</p>
 <h2 id="toc17">Conversion</h2>
<p>To convert txt to html, drag and drop your .txt file on .bat file.</p>
<p>You can then convert .html to .mobi using kindlegen:<br><code><br>kindlegen.exe "Test Author - Series Name - 3 - Best Book.html" -dont_append_source -o "Test Author - Series Name - 3 - Best Book.mobi"<br></code></p>
<p>or use pandoc to convert .html to .epub:<br><code><br>pandoc.exe "Test Author - Series Name - 3 - Best Book.html" -s -o "Test Author - Series Name - 3 - Best Book.epub"<br></code></p>
<p>And then use kindlegen to convert .epub to .mobi:<br><code><br>kindlegen.exe "Test Author - Series Name - 3 - Best Book.epub" -dont_append_source -o "Test Author - Series Name - 3 - Best Book.mobi"<br></code></p>
<p>You can also use calibre:<br><code><br>ebook-convert.exe "Test Author - Series Name - 3 - Best Book.html" "Test Author - Series Name - 3 - Best Book.epub"<br></code><br>or<br><code><br>ebook-convert.exe "Test Author - Series Name - 3 - Best Book.epub" "Test Author - Series Name - 3 - Best Book.mobi"<br></code></p>
 <h2 id="toc18">Html editors:</h2>
<p>-1stPage2000 <a href="https://mega.nz/folder/xGESQQYL#rAlBgQ6QM-FJUhFdXW7Z5g">https://mega.nz/folder/xGESQQYL#rAlBgQ6QM-FJUhFdXW7Z5g</a><br>-Seamonkey (Look in menu "windows/composer") <a href="https://www.seamonkey-project.org/">https://www.seamonkey-project.org/</a></p>
 <h2 id="toc19">Text editor:</h2>
<p>-Notepad++ <a href="https://notepad-plus-plus.org/">https://notepad-plus-plus.org/</a></p>
<p>If you are reading this on github, this README.md was made by copy pasting html file source from notepad++, and removing prefix text containing styles.</p>
 <a id="helpertop1" href="#helperbottom1"></a>          <div id="fb1"><a href="#f1">1.</a> Kindlegen can be found in the Kindle previewer package, unzip the installation and look for kindlegen.exe</div>                 <a id="helperbottom1" href="#helpertop1"></a>
 <a id="helpertop2" href="#helperbottom2"></a>          <div id="fb2"><a href="#f2">2.</a> Footnotes are ...</div>                 <a id="helperbottom2" href="#helpertop2"></a>
</body>
