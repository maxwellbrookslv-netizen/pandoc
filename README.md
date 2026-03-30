<!-- 请勿编辑此文件。它是根据
README.template 和 MANUAL.txt 通过以下命令自动生成的：
pandoc --lua-filter tools/update-readme.lua README.template -o README.md
-->

# Pandoc

[![github
release](https://img.shields.io/github/release/jgm/pandoc.svg?label=current+release)](https://github.com/jgm/pandoc/releases)
[![hackage
release](https://img.shields.io/hackage/v/pandoc.svg?label=hackage)](https://hackage.haskell.org/package/pandoc)
[![homebrew](https://img.shields.io/homebrew/v/pandoc.svg)](https://formulae.brew.sh/formula/pandoc)
[![stackage LTS
package](https://stackage.org/package/pandoc/badge/lts)](https://www.stackage.org/lts/package/pandoc)
[![CI
tests](https://github.com/jgm/pandoc/workflows/CI%20tests/badge.svg)](https://github.com/jgm/pandoc/actions)
[![license](https://img.shields.io/badge/license-GPLv2+-lightgray.svg)](https://www.gnu.org/licenses/gpl.html)
[![pandoc-discuss on google
groups](https://img.shields.io/badge/pandoc-discuss-red.svg?style=social)](https://groups.google.com/forum/#!forum/pandoc-discuss)

## 通用标记转换器

Pandoc 是一个 [Haskell](https://haskell.org) 库，用于将一种标记格式转换为另一种格式，以及一个使用此库的命令行工具。

它可以转换 *从*

<div id="input-formats">

- `asciidoc` ([AsciiDoc](https://asciidoc.org/) 标记)
- `bibtex` ([BibTeX](https://ctan.org/pkg/bibtex) 参考文献)
- `biblatex` ([BibLaTeX](https://ctan.org/pkg/biblatex) 参考文献)
- `bits` ([BITS](https://jats.nlm.nih.gov/extensions/bits/) XML，别名为 `jats`)
- `commonmark` ([CommonMark](https://commonmark.org) Markdown)
- `commonmark_x` ([CommonMark](https://commonmark.org) Markdown 扩展)
- `creole` ([Creole 1.0](http://www.wikicreole.org/wiki/Creole1.0))
- `csljson` ([CSL
  JSON](https://citeproc-js.readthedocs.io/en/latest/csl-json/markup.html)
  参考文献)
- `csv` ([CSV](https://tools.ietf.org/html/rfc4180) 表格)
- `tsv`
  ([TSV](https://www.iana.org/assignments/media-types/text/tab-separated-values)
  表格)
- `djot` ([Djot 标记](https://djot.net))
- `docbook` ([DocBook](https://docbook.org))
- `docx` ([Word docx](https://en.wikipedia.org/wiki/Office_Open_XML))
- `dokuwiki` ([DokuWiki 标记](https://www.dokuwiki.org/dokuwiki))
- `endnotexml` ([EndNote XML
  参考文献](https://support.clarivate.com/Endnote/s/article/EndNote-XML-Document-Type-Definition))
- `epub` ([EPUB](http://idpf.org/epub))
- `fb2`
  ([FictionBook2](http://www.fictionbook.org/index.php/Eng:XML_Schema_Fictionbook_2.1)
  电子书)
- `gfm` ([GitHub-Flavored
  Markdown](https://help.github.com/articles/github-flavored-markdown/))，
  或已弃用的且不太准确的 `markdown_github`；仅在需要
  [`markdown_github`](https://pandoc.org/MANUAL.html#markdown-variants)
  支持但 [`gfm`](https://pandoc.org/MANUAL.html#markdown-variants) 不支持的扩展时使用。
- `haddock` ([Haddock
  标记](https://www.haskell.org/haddock/doc/html/ch03s08.html))
- `html` ([HTML](https://www.w3.org/html/))
- `ipynb` ([Jupyter
  notebook](https://nbformat.readthedocs.io/en/latest/))
- `jats` ([JATS](https://jats.nlm.nih.gov) XML)
- `jira`
  ([Jira](https://jira.atlassian.com/secure/WikiRendererHelpAction.jspa?section=all)/Confluence
  wiki 标记)
- `json` (JSON 版本的本机 AST)
- `latex` ([LaTeX](https://www.latex-project.org/))
- `markdown` ([Pandoc 的
  Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown))
- `markdown_mmd`
  ([MultiMarkdown](https://fletcherpenney.net/multimarkdown/))
- `markdown_phpextra` ([PHP Markdown
  Extra](https://michelf.ca/projects/php-markdown/extra/))
- `markdown_strict` (原始未扩展的
  [Markdown](https://daringfireball.net/projects/markdown/))
- `mediawiki` ([MediaWiki
  标记](https://www.mediawiki.org/wiki/Help:Formatting))
- `man` ([roff man](https://man.cx/groff_man(7)))
- `mdoc` ([mdoc](https://mandoc.bsd.lv/man/mdoc.7.html) 手册页标记)
- `muse` ([Muse](https://amusewiki.org/library/manual))
- `native` (本机 Haskell)
- `odt` ([OpenDocument 文本
  文档](https://en.wikipedia.org/wiki/OpenDocument))
- `opml` ([OPML](https://opml.org/spec2.opml))
- `org` ([Emacs Org mode](https://orgmode.org))
- `pod` (Perl 的 [Plain Old
  Documentation](https://perldoc.perl.org/perlpod))
- `pptx`
  ([PowerPoint](https://en.wikipedia.org/wiki/Microsoft_PowerPoint))
- `ris` ([RIS](https://en.wikipedia.org/wiki/RIS_(file_format))
  参考文献)
- `rtf` ([Rich Text
  Format](https://en.wikipedia.org/wiki/Rich_Text_Format))
- `rst`
  ([reStructuredText](https://docutils.sourceforge.io/docs/ref/rst/introduction.html))
- `t2t` ([txt2tags](https://txt2tags.org))
- `textile` ([Textile](https://textile-lang.com))
- `tikiwiki` ([TikiWiki
  标记](https://doc.tiki.org/Wiki-Syntax-Text#The_Markup_Language_Wiki-Syntax))
- `twiki` ([TWiki
  标记](https://twiki.org/cgi-bin/view/TWiki/TextFormattingRules))
- `typst` ([typst](https://typst.app))
- `vimwiki` ([Vimwiki](https://vimwiki.github.io))
- `xlsx` ([Excel
  电子表格](https://en.wikipedia.org/wiki/Microsoft_Excel#File_formats))
- `xml` (XML 版本的本机 AST)
- 自定义 Lua 阅读器的路径，请参见下面的 [自定义阅读器和
  编写器](https://pandoc.org/MANUAL.html#custom-readers-and-writers)

</div>

它可以转换 *到*

<div id="output-formats">

- `ansi` (带有 [ANSI 转义
  码](https://en.wikipedia.org/wiki/ANSI_escape_code) 的文本，用于终端查看)
- `asciidoc` (现代 [AsciiDoc](https://asciidoc.org/)，由
  [AsciiDoctor](https://asciidoctor.org/) 解释)
- `asciidoc_legacy` ([AsciiDoc](https://asciidoc.org/)，由
  [`asciidoc-py`](https://github.com/asciidoc-py/asciidoc-py) 解释)。
- `asciidoctor` (已弃用的 `asciidoc` 同义词)
- `bbcode` [BBCode](https://www.bbcode.org/reference.php)
- `bbcode_fluxbb` [BBCode
  (FluxBB)](https://web.archive.org/web/20210623155046/https://fluxbb.org/forums/help.php#bbcode)
- `bbcode_phpbb` [BBCode
  (phpBB)](https://www.phpbb.com/community/help/bbcode)
- `bbcode_steam` [BBCode
  (Steam)](https://steamcommunity.com/comment/ForumTopic/formattinghelp)
- `bbcode_hubzilla` [BBCode
  (Hubzilla)](https://hubzilla.org/help/member/bbcode)
- `bbcode_xenforo` [BBCode
  (xenForo)](https://www.xenfocus.com/community/help/bb-codes/)
- `beamer` ([LaTeX beamer](https://ctan.org/pkg/beamer) 幻灯片演示)
- `bibtex` ([BibTeX](https://ctan.org/pkg/bibtex) 参考文献)
- `biblatex` ([BibLaTeX](https://ctan.org/pkg/biblatex) 参考文献)
- `chunkedhtml` (多个链接 HTML 文件的 zip 存档)
- `commonmark` ([CommonMark](https://commonmark.org) Markdown)
- `commonmark_x` ([CommonMark](https://commonmark.org) Markdown 扩展)
- `context` ([ConTeXt](https://www.contextgarden.net/))
- `csljson` ([CSL
  JSON](https://citeproc-js.readthedocs.io/en/latest/csl-json/markup.html)
  参考文献)
- `djot` ([Djot 标记](https://djot.net))
- `docbook` 或 `docbook4` ([DocBook](https://docbook.org) 4)
- `docbook5` (DocBook 5)
- `docx` ([Word docx](https://en.wikipedia.org/wiki/Office_Open_XML))
- `dokuwiki` ([DokuWiki 标记](https://www.dokuwiki.org/dokuwiki))
- `epub` 或 `epub3` ([EPUB](http://idpf.org/epub) v3 书籍)
- `epub2` (EPUB v2)
- `fb2`
  ([FictionBook2](http://www.fictionbook.org/index.php/Eng:XML_Schema_Fictionbook_2.1)
  电子书)
- `gfm` ([GitHub-Flavored
  Markdown](https://help.github.com/articles/github-flavored-markdown/))，
  或已弃用的且不太准确的 `markdown_github`；仅在需要
  [`markdown_github`](https://pandoc.org/MANUAL.html#markdown-variants)
  支持但 [`gfm`](https://pandoc.org/MANUAL.html#markdown-variants) 不支持的扩展时使用。
- `haddock` ([Haddock
  标记](https://www.haskell.org/haddock/doc/html/ch03s08.html))
- `html` 或 `html5` ([HTML](https://www.w3.org/html/)，
  即 [HTML5](https://html.spec.whatwg.org/)/XHTML [多语言
  标记](https://www.w3.org/TR/html-polyglot/))
- `html4` ([XHTML](https://www.w3.org/TR/xhtml1/) 1.0 Transitional)
- `icml` ([InDesign
  ICML](https://web.archive.org/web/20211006210211/https://wwwimages.adobe.com/www.adobe.com/content/dam/acom/en/devnet/indesign/sdk/cs6/idml/idml-cookbook.pdf))
- `ipynb` ([Jupyter
  notebook](https://nbformat.readthedocs.io/en/latest/))
- `jats_archiving` ([JATS](https://jats.nlm.nih.gov) XML，存档和
  交换标签集)
- `jats_articleauthoring` ([JATS](https://jats.nlm.nih.gov) XML，文章
  创作标签集)
- `jats_publishing` ([JATS](https://jats.nlm.nih.gov) XML，期刊
  出版标签集)
- `jats` ( `jats_archiving` 的别名)
- `jira`
  ([Jira](https://jira.atlassian.com/secure/WikiRendererHelpAction.jspa?section=all)/Confluence
  wiki 标记)
- `json` (JSON 版本的本机 AST)
- `latex` ([LaTeX](https://www.latex-project.org/))
- `man` ([roff man](https://man.cx/groff_man(7)))
- `markdown` ([Pandoc 的
  Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown))
- `markdown_mmd`
  ([MultiMarkdown](https://fletcherpenney.net/multimarkdown/))
- `markdown_phpextra` ([PHP Markdown
  Extra](https://michelf.ca/projects/php-markdown/extra/))
- `markdown_strict` (原始未扩展的
  [Markdown](https://daringfireball.net/projects/markdown/))
- `markua` ([Markua](https://leanpub.com/markua/read))
- `mediawiki` ([MediaWiki
  标记](https://www.mediawiki.org/wiki/Help:Formatting))
- `ms` ([roff ms](https://man.cx/groff_ms(7)))
- `muse` ([Muse](https://amusewiki.org/library/manual))
- `native` (本机 Haskell)
- `odt` ([OpenDocument 文本
  文档](https://en.wikipedia.org/wiki/OpenDocument))
- `opml` ([OPML](https://opml.org/spec2.opml))
- `opendocument` ([OpenDocument
  XML](https://www.oasis-open.org/2021/06/16/opendocument-v1-3-oasis-standard-published/))
- `org` ([Emacs Org mode](https://orgmode.org))
- `pdf` ([PDF](https://www.adobe.com/pdf/))
- `plain` (纯文本)
- `pptx`
  ([PowerPoint](https://en.wikipedia.org/wiki/Microsoft_PowerPoint)
  幻灯片演示)
- `rst`
  ([reStructuredText](https://docutils.sourceforge.io/docs/ref/rst/introduction.html))
- `rtf` ([Rich Text
  Format](https://en.wikipedia.org/wiki/Rich_Text_Format))
- `texinfo` ([GNU Texinfo](https://www.gnu.org/software/texinfo/))
- `textile` ([Textile](https://textile-lang.com))
- `slideous` ([Slideous](https://goessner.net/articles/slideous/) HTML
  和 JavaScript 幻灯片演示)
- `slidy` ([Slidy](https://www.w3.org/Talks/Tools/Slidy2/) HTML 和
  JavaScript 幻灯片演示)
- `dzslides` ([DZSlides](https://paulrouget.com/dzslides/) HTML5 +
  JavaScript 幻灯片演示)
- `revealjs` ([reveal.js](https://revealjs.com/) HTML5 + JavaScript
  幻灯片演示)
- `s5` ([S5](https://meyerweb.com/eric/tools/s5/) HTML 和 JavaScript
  幻灯片演示)
- `tei` ([TEI Simple](https://github.com/TEIC/TEI-Simple))
- `typst` ([typst](https://typst.app))
- `vimdoc`
  ([Vimdoc](https://vimhelp.org/helphelp.txt.html#help-writing))
- `xml` (XML 版本的本机 AST)
- `xwiki` ([XWiki
  标记](https://www.xwiki.org/xwiki/bin/view/Documentation/UserGuide/Features/XWikiSyntax/))
- `zimwiki` ([ZimWiki
  标记](https://zim-wiki.org/manual/Help/Wiki_Syntax.html))
- 自定义 Lua 编写器的路径，请参见下面的 [自定义阅读器和
  编写器](https://pandoc.org/MANUAL.html#custom-readers-and-writers)

</div>

Pandoc 也可以通过 LaTeX、Groff ms 或 HTML 生成 PDF 输出。

Pandoc 的增强版 Markdown 包括表格、定义列表、元数据块、脚注、引用、数学等语法。参见下面的用户手册中的 [Pandoc 的
Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown)。

Pandoc 具有模块化设计：它由一组阅读器组成，这些阅读器解析给定格式的文本并生成文档的本机表示（*抽象语法树* 或 AST），以及一组编写器，这些编写器将此本机表示转换为目标格式。因此，添加输入或输出格式只需要添加阅读器或编写器。用户还可以运行自定义 pandoc 过滤器来修改中间 AST（请参见 [过滤器](https://pandoc.org/filters.html) 和
[Lua 过滤器](https://pandoc.org/lua-filters.html) 的文档）。

由于 pandoc 的文档中间表示不如它转换之间的许多格式表达力强，人们不应该期望每种格式与每种其他格式之间的完美转换。Pandoc 试图保留文档的结构元素，但不保留格式细节，如边距大小。有些文档元素，如复杂表格，可能不适合 pandoc 的简单文档模型。虽然从 pandoc 的 Markdown 到所有格式的转换力求完美，但从比 pandoc 的 Markdown 更具表达力的格式转换可能会丢失信息。

## 安装

这里是 [如何安装 pandoc](INSTALL.md)。

## 文档

Pandoc 的网站包含完整的 [用户
指南](https://pandoc.org/MANUAL.html)。它也作为 pandoc 风格的 Markdown 在
[这里](MANUAL.txt) 提供。网站还包含一些 [pandoc 使用
示例](https://pandoc.org/demos.html)、有限的 [在线
演示](https://pandoc.org/try) 和基于 [WebAssembly 的在线
演示](https://pandoc.org/app)。

## 贡献

欢迎拉取请求、错误报告和功能请求。请确保在打开新问题之前阅读 [贡献者指南](CONTRIBUTING.md)。

## 许可证

© 2006-2024 John MacFarlane (jgm@berkeley.edu)。根据
[GPL](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html "GNU General Public License")，
版本 2 或更高版本发布。此软件不提供任何形式的保证。
（完整版权和保证声明请参见 COPYRIGHT。）
