# Markdown
マークダウンのサンプルでは、マークダウンファイルの書き方を紹介しています。このドキュメントでは、コアシンタックスと拡張機能（GMF）を統合しています。

* [Block Elements](#block-elements)
  * [段落と改行](#段落と改行)
  * [見出し](#見出し)
  * [引用](#引用)
  * [リスト](#リスト)
  * [コードブロック](#コードブロック)
  * [Horizontal Rules](#horizontal-rules)
  * [Table](#table)
* [Span Elements](#span-elements)
  * [Links](#links)
  * [Emphasis](#emphasis)
  * [Code](#code)
  * [Images](#images)
  * [Strikethrough](#strikethrough)
* [Miscellaneous](#miscellaneous)
  * [Automatic Links](#automatic-links)
  * [Backslash Escapes](#backslash-escapes)
* [Inline HTML](#inline-html)

## Block Elements
### 段落と改行
#### 段落
HTML Tag: `<p>`

1行以上の空白行。 (空白行とは、何も書かれていない行のことです。  スペース　または　タブ　は空白とみなします。)

Code:

    This will be 
    inline.
    
    This is second paragraph.
Preview:
***
This will be 
inline.

This is second paragraph.
***
#### 改行
HTML Tag: `<br />`

行の最後に、スペースを２つ以上入れる。

Code:

    This will be not  
    inline.
Preview:
***
This will be not  
inline.
***


### 見出し
見出し表記には、２つの方法があります。

#### 下線を引いて表記する方法
HTML Tags: `<h1>`, `<h2>`

等号記号（＝）を下線に引くと `<h1>` として表示されます。
ハイフン記号（-)を下線に引くと `<h2>` として表示されます。

Code:

    This is an H1
    =============
    This is an H2
    -------------
Preview:
***
This is an H1
=============

This is an H2
-------------
***
#### ハッシュタグを使用する方法
HTML Tags: `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`

**ハッシュ記号 (#)** を、1個は`<h1>`、2個は`<h2>`。6個まで使えます。

Code:

    # This is an H1
    ## This is an H2
    ###### This is an H6
Preview:
***
# This is an H1
## This is an H2
###### This is an H6
***
見出しを閉じる時に、ハッシュ記号を使うことができます。（数は対応しなくて良いです）

Code:

    # This is an H1 #
    ## This is an H2 ##
    ### This is an H3 ######
Preview:
***
# This is an H1 #
## This is an H2 ##
### This is an H3 ######
***


### Blockquotes
HTML Tag: `<blockquote>`

マークダウンでは、メールで引用を表す時に使う　**>** 記号を使います。 
テキストを、ハードラップし、全ての行の前に、> を使うと見栄えが良いです。

Code:

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    > Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
    > 
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    > id sem consectetuer libero luctus adipiscing.
Preview:
***
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

***
マークダウンは、段落の最初の行の前に、　> 記号を記すだけでも、引用を表示してくれます。

Code:

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
    
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    id sem consectetuer libero luctus adipiscing.
Preview:
***
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.

***
引用は、子要素の引用を持つことができ、>>　と　> 記号を増やして表現できます。

Code:

    > This is the first level of quoting.
    >
    > > This is nested blockquote.
    >
    > Back to the first level.
Preview:
***
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.

***
引用では、他のマークダウン要素、見出しやリストやブロックコードなどを使うことができます。

Code:

    > ## This is a header.
    > 
    > 1.   This is the first list item.
    > 2.   This is the second list item.
    > 
    > Here's some example code:
    > 
    >     return shell_exec("echo $input | $markdown_script");
Preview:
***
> ## This is a header.
> 
> 1.   This is the first list item.
> 2.   This is the second list item.
> 
> Here's some example code:
> 
>     return shell_exec("echo $input | $markdown_script");

***

### リスト
Markdownは順序付き（番号付き）リストと順序なし（箇条書き）リストをサポートしています。

#### 箇条書き

HTML Tag: `<ul>`

箇条書きは、 **(*)**, **(+)**, and **(-)**　を使います。

Code:

    *   Red
    *   Green
    *   Blue
Preview:
***
*   Red
*   Green
*   Blue

***
同様に

Code:

    +   Red
    +   Green
    +   Blue
and:

Code:

    -   Red
    -   Green
    -   Blue
#### 番号付き
HTML Tag: `<ol>`

番号付きリストは、数字+.(ピリオド）を使います。

Code:

    1.  Bird
    2.  McHale
    3.  Parish
Preview:
***
1.  Bird
2.  McHale
3.  Parish

***
数字とピリオドは、間違って、番号付きリストのように表示されることがありますので、リスト出ないときは、バックスラッシュを表記して、リスト表示させないようにしましょう。

Code:

    1986. What a great season.
Preview:
***
1986. What a great season.

***
バックスラッシュ ** (\\)** を、ピリオドの前に書きます。

Code:

    1986\. What a great season.
Preview:
***
1986\. What a great season.

***
#### インデント

##### 引用
引用をリストアイテム内に配置するには、引用の > 区切り文字をインデントする必要があります。

Code:

    *   A list item with a blockquote:

        > This is a blockquote
        > inside a list item.
Preview:
***
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.

***
##### コードブロック
リストアイテムの中に、コードブロックを表示するには、8個のスペース**8 spaces** か、2個のタブ**two tabs**を入れます。

Code:

    *   A list item with a code block:

            <code goes here>
Preview:
***
*   A list item with a code block:

        <code goes here>

***
##### ネスト化されたリスト
Code:

    * A
      * A1
      * A2
    * B
    * C
Preview:
***
* A
  * A1
  * A2
* B
* C

***
### コードブロック
HTML Tag: `<pre>`

Indent every line of the block by at least **4 spaces** or **1 tab**.

Code:

    This is a normal paragraph:

        This is a code block.
Preview:
***
This is a normal paragraph:

    This is a code block.
***
A code block continues until it reaches a line that is not indented (or the end of the article).

Within a code block, ***ampersands (&)*** and angle **brackets (< and >)** are automatically converted into HTML entities.

Code:

        <div class="footer">
            &copy; 2004 Foo Corporation
        </div>
Preview:
***
    <div class="footer">
        &copy; 2004 Foo Corporation
    </div>
***
Following sections Fenced Code Blocks and Syntax Highlighting are extensions, you can use the other way to write the code block.
#### Fenced Code Blocks
Just wrap your code in ```` ``` ```` (as shown below) and you won't need to indent it by four spaces.

Code:

    Here's an example:

    ```
    function test() {
      console.log("notice the blank line before this function?");
    }
    ```
Preview:
***
Here's an example:

```
function test() {
  console.log("notice the blank line before this function?");
}
```
***
#### Syntax Highlighting
In your fenced block, add an optional language identifier and we'll run it through syntax highlighting ([Support Languages](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)).

Code:

    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```
Preview:
***
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
***
### Horizontal Rules
HTML Tag: `<hr />`
Places **three or more hyphens (-), asterisks (*), or underscores (_)** on a line by themselves. You may use spaces between the hyphens or asterisks.

Code:

    * * *
    ***
    *****
    - - -
    ---------------------------------------
    ___
Preview:
***
* * *
***
*****
- - -
---------------------------------------
___
***
### Table
HTML Tag: `<table>`

It's an extension.

Separates column by **pipe (|)** and header by **dashes (-)**, and uses **colon (:)** for alignment.

The outer **pipes (|)** and alignment are optional. There are **3 delimiters** each cell at least for separating header.

Code:
```
| Left | Center | Right |
|:-----|:------:|------:|
|aaa   |bbb     |ccc    |
|ddd   |eee     |fff    |

 A | B 
---|---
123|456


A |B 
--|--
12|45
```
Preview:
***
| Left | Center | Right |
|:-----|:------:|------:|
|aaa   |bbb     |ccc    |
|ddd   |eee     |fff    |

 A | B 
---|---
123|456

A |B 
--|--
12|45
***
## Span Elements
### Links
HTML Tag: `<a>`

Markdown supports two style of links: inline and reference.

#### Inline
Inline link format like this: `[Link Text](URL "Title")`

Title is optional.

Code:

    This is [an example](http://example.com/ "Title") inline link.
    
    [This link](http://example.net/) has no title attribute.
Preview:
***
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
***
If you’re referring to a local resource on the same server, you can use relative paths:

Code:

    See my [About](/about/) page for details. 
Preview:
***
See my [About](/about/) page for details. 
***
#### Reference
You could predefine link references. Format like this: `[id]: URL "Title"`

Title is also optional. And the you refer the link, format like this: `[Link Text][id]`

Code:

    [id]: http://example.com/  "Optional Title Here"
    This is [an example][id] reference-style link.
Preview:
***
[id]: http://example.com/  "Optional Title Here"
This is [an example][id] reference-style link.
***
That is:

* Square brackets containing the link identifier (**not case sensitive**, optionally indented from the left margin using up to three spaces);
* followed by a colon;
* followed by one or more spaces (or tabs);
* followed by the URL for the link;
* The link URL may, optionally, be surrounded by angle brackets.
* optionally followed by a title attribute for the link, enclosed in double or single quotes, or enclosed in parentheses.

The following three link definitions are equivalent:

Code:

    [foo]: http://example.com/  "Optional Title Here"
    [foo]: http://example.com/  'Optional Title Here'
    [foo]: http://example.com/  (Optional Title Here)
    [foo]: <http://example.com/>  "Optional Title Here"
Uses an empty set of square brackets, the link text itself is used as the name.

Code:

    [Google]: http://google.com/
    [Google][]
Preview:
***
[Google]: http://google.com/
[Google][]
***
### Emphasis
HTML Tags: `<em>`, `<strong>`

Markdown treats **asterisks (*)** and **underscores (_)** as indicators of emphasis. **One delimiter** will be  `<em>`; **double delimiters* will be `<strong>`.

Code:

    *single asterisks*

    _single underscores_

    **double asterisks**

    __double underscores__
Preview:
***
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
***
But if you surround an * or _ with spaces, it’ll be treated as a literal asterisk or underscore.

You can backslash escape it:

Code:

    \*this text is surrounded by literal asterisks\*
Preview:
***
\*this text is surrounded by literal asterisks\*
***
### Code
HTML Tag: `<code>`

Wraps it with **backtick quotes (`)**.

Code:

    Use the `printf()` function.
Preview:
***
Use the `printf()` function.
***
To include a literal backtick character within a code span, you can use **multiple backticks** as the opening and closing delimiters:

Code:

    ``There is a literal backtick (`) here.``
Preview:
***
``There is a literal backtick (`) here.``
***
The backtick delimiters surrounding a code span may include spaces — one after the opening, one before the closing. This allows you to place literal backtick characters at the beginning or end of a code span:

Code:

    A single backtick in a code span: `` ` ``

    A backtick-delimited string in a code span: `` `foo` ``
Preview:
***
A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
***
### Images
HTML Tag: `<img />`

Markdown uses an image syntax that is intended to resemble the syntax for links, allowing for two styles: inline and reference.
#### Inline

Inline image syntax looks like this: `![Alt text](URL "Title")`

Title is optional.

Code:

    ![Alt text](/path/to/img.jpg)

    ![Alt text](/path/to/img.jpg "Optional title")
Preview:
***
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
***
That is:

* An exclamation mark: !;
* followed by a set of square brackets, containing the alt attribute text for the image;
* followed by a set of parentheses, containing the URL or path to the image, and an optional title attribute enclosed in double or single quotes.

#### Reference
Reference-style image syntax looks like this: `![Alt text][id]`

Code:

    [img id]: url/to/image  "Optional title attribute"
    ![Alt text][img id]
Preview:
***
[img id]: url/to/image  "Optional title attribute"
![Alt text][img id]
***
### Strikethrough
HTML Tag: `<del>`

It's an extension.

GFM adds syntax to strikethrough text.

Code:
```
~~Mistaken text.~~
```
Preview:
***
~~Mistaken text.~~
***
## Miscellaneous
### Automatic Links
Markdown supports a shortcut style for creating “automatic” links for URLs and email addresses: simply surround the URL or email address with angle brackets. 

Code:

    <http://example.com/>
    
    <address@example.com>
Preview:
***
<http://example.com/>

<address@example.com>
***
GFM will autolink standard URLs.

Code:
```
https://github.com/emn178/markdown
```
Preview:
***
https://github.com/emn178/markdown
***

### Backslash Escapes
Markdown allows you to use backslash escapes to generate literal characters which would otherwise have special meaning in Markdown’s formatting syntax.

Code:

    \*literal asterisks\*
Preview:
***
\*literal asterisks\*
***
Markdown provides backslash escapes for the following characters:

Code:

    \   backslash
    `   backtick
    *   asterisk
    _   underscore
    {}  curly braces
    []  square brackets
    ()  parentheses
    #   hash mark
    +   plus sign
    -   minus sign (hyphen)
    .   dot
    !   exclamation mark

## Inline HTML
For any markup that is not covered by Markdown’s syntax, you simply use HTML itself. There’s no need to preface it or delimit it to indicate that you’re switching from Markdown to HTML; you just use the tags.

Code:

    This is a regular paragraph.

    <table>
        <tr>
            <td>Foo</td>
        </tr>
    </table>

    This is another regular paragraph.
Preview:
***
This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.
***
Note that Markdown formatting syntax is **not processed within block-level HTML tags**. 

Unlike block-level HTML tags, Markdown syntax is **processed within span-level tags**.

Code:

    <span>**Work**</span>
    
    <div>
        **No Work**
    </div>
Preview:
***
<span>**Work**</span>

<div>
  **No Work**
</div>
***
