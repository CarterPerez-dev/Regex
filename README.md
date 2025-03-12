# 1000 Useful Regex

### 1. Find All Words in Parentheses
```regex
\(([^()]+)\)
```
Matches text inside a single pair of parentheses.

---------------------------------------

### 2. Replace With a “Negative Space” (Example)
```regex
-1 $1
```
Example placeholder for a custom replacement operation involving `-1`.

---------------------------------------

### 3. Replace MongoSh Object IDs
```regex
^\s*_id:\s*ObjectId\("[^"]+"\),?\s*(?:\r?\n)?
```
Find lines with `ObjectId("...")` at the start (accounting for indentation).

---------------------------------------

### 4. Move Spaces to the Beginning (Example)
```regex
^( {4})
```
Matches exactly 4 leading spaces at the start of a line for an example shift.

---------------------------------------

### 5. Remove `/* ... */`-Style Comments
```regex
\/\*[\s\S]*?\*\/(\s*\n)?
```
Removes multiline comments (including any optional trailing whitespace/newline).

---------------------------------------

### 6. Remove Empty Lines
```regex
^[ \t]*\n
```
Deletes any line consisting of only spaces or tabs.

---------------------------------------

### 7. Match a Valid Email Address
```regex
[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}
```
Locates common email address formats.

---------------------------------------

### 8. Match a URL (HTTP/HTTPS)
```regex
https?:\/\/[^\s/$.?#].[^\s]*
```
Finds web addresses starting with `http` or `https`.

---------------------------------------

### 9. Match Any 5-Digit US ZIP Code
```regex
\b\d{5}\b
```
Locates 5-digit ZIP codes.

---------------------------------------

### 10. Match US ZIP+4 Code
```regex
\b\d{5}-\d{4}\b
```
Locates ZIP codes in the `12345-6789` format.

---------------------------------------

### 11. Match a 24-Hour Time
```regex
\b([01]\d|2[0-3]):[0-5]\d\b
```
Finds times like `00:00` through `23:59`.

---------------------------------------

### 12. Match a 12-Hour Time With AM/PM
```regex
\b(0[1-9]|1[0-2]):[0-5]\d\s?(AM|PM)\b
```
Captures times from `01:00 AM` to `12:59 PM`.

---------------------------------------

### 13. Match Common Date Format (MM/DD/YYYY)
```regex
\b(0[1-9]|1[0-2])/(0[1-9]|[12]\d|3[01])/\d{4}\b
```
Finds dates in US style. Example: `12/31/2025`.

---------------------------------------

### 14. Match Words Separated by a Single Space
```regex
^[A-Za-z]+(?: [A-Za-z]+)*$
```
Ensures a line has only words and single spaces.

---------------------------------------

### 15. Remove Leading Zeros (on numbers)
```regex
\b0+(\d+)\b
```
Captures numbers with leading zeros (e.g. `007` -> `7`).

---------------------------------------

### 16. Match Trailing Whitespace
```regex
[ \t]+$
```
Finds any trailing spaces or tabs at the end of a line.

---------------------------------------

### 17. Remove All Non-ASCII Characters
```regex
[^\x00-\x7F]+
```
Deletes characters outside standard ASCII.

---------------------------------------

### 18. Strip All HTML Tags
```regex
<[^>]*>
```
Finds any `<tag>` sequences.

---------------------------------------

### 19. Match a Single IPv4 Address
```regex
\b((25[0-5]|2[0-4]\d|[01]?\d?\d)\.){3}(25[0-5]|2[0-4]\d|[01]?\d?\d)\b
```
Captures IPv4 in dotted notation (0.0.0.0 to 255.255.255.255).

---------------------------------------

### 20. Match a Phone Number (North America Basic)
```regex
\(?\b\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}\b
```
Matches phone numbers like `123-456-7890`, `(123) 456-7890`, etc.

---------------------------------------

### 21. Match a Strong Password (Example)
```regex
^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*\W).{8,}$
```
Requires at least 8 characters, uppercase, lowercase, digit, and symbol.

---------------------------------------

### 22. Match Lines Starting With a Capital Letter
```regex
^[A-Z].*
```
Captures lines where the first character is uppercase.

---------------------------------------

### 23. Match Lines Ending With a Period
```regex
^.*\.$
```
Captures lines that end in a dot (`.`).

---------------------------------------

### 24. Capture Two or More Consecutive Spaces
```regex
 {2,}
```
Finds double (or more) spaces.

---------------------------------------

### 25. Replace Multiple Spaces With a Single Space
```regex
 {2,}
```
Use with replacement string `" "` to compress spaces.

---------------------------------------

### 26. Match CamelCase Words
```regex
([A-Z][a-z0-9]+)+
```
Captures typical CamelCase patterns.

---------------------------------------

### 27. Match snake_case Words
```regex
^[a-z0-9]+(?:_[a-z0-9]+)*$
```
Locates lines of snake_case text.

---------------------------------------

### 28. Match kebab-case Words
```regex
^[a-z0-9]+(?:-[a-z0-9]+)*$
```
Locates lines of kebab-case text.

---------------------------------------

### 29. Capture Duplicate Words in a Row
```regex
\b(\w+)\s+\1\b
```
Finds repeated words like “cat cat”.

---------------------------------------

### 30. Capture 3 or More Repeated Characters
```regex
(.)\1{2,}
```
Finds any character repeated 3+ times (e.g., `aaa` or `!!!!`).

---------------------------------------

### 31. Validate a Simple Username
```regex
^[A-Za-z0-9_]{3,16}$
```
Ensures 3-16 alphanumeric or underscore characters.

---------------------------------------

### 32. Match a Twitter Handle
```regex
@([A-Za-z0-9_]{1,15})
```
Captures a typical Twitter username after `@`.

---------------------------------------

### 33. Match a Hashtag
```regex
#[A-Za-z0-9_]+
```
Finds strings starting with `#` followed by letters, digits, or underscores.

---------------------------------------

### 34. Match Simple Hex Color Codes
```regex
#[A-Fa-f0-9]{6}\b
```
Locates 6-digit hex colors (e.g., `#FF0033`).

---------------------------------------

### 35. Match Short Hex Color Codes
```regex
#[A-Fa-f0-9]{3}\b
```
Locates 3-digit hex colors (e.g., `#FFF`).

---------------------------------------

### 36. Strip Markdown Links
```regex
\[(.*?)\]\((.*?)\)
```
Captures `[text](link)` patterns in Markdown.

---------------------------------------

### 37. Match a Simple GUID/UUID (Version 4-like)
```regex
[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}
```
Captures a 36-character UUID-like string.

---------------------------------------

### 38. Find Start/End Double Quotes
```regex
"([^"]*)"
```
Matches pairs of double quotes around text.

---------------------------------------

### 39. Match Square-Bracketed Text
```regex
\[(.*?)\]
```
Captures text inside `[...]`.

---------------------------------------

### 40. Remove HTML Entities
```regex
&[a-zA-Z0-9]+;
```
Finds sequences like `&nbsp;` or `&amp;`.

---------------------------------------

### 41. Find All Decimal Numbers
```regex
\d+(\.\d+)?
```
Captures integers or floats like `123` or `123.45`.

---------------------------------------

### 42. Match a Single or Double Quoted String
```regex
(['"])(?:(?=(\\?))\2.)*?\1
```
Finds quoted strings with possible escaped quotes.

---------------------------------------

### 43. Match a Non-Capturing Group of Letters
```regex
(?:[A-Za-z]+)
```
Non-capturing group for letters.

---------------------------------------

### 44. Remove Duplicate Lines (Regex Approach in Some Editors)
```regex
^(.*)(\r?\n\1)+$
```
With certain “replace with `\1`” logic in some tools, leaves only one occurrence.

---------------------------------------

### 45. Match Words With Apostrophes
```regex
[A-Za-z]+('[A-Za-z]+)?
```
Captures words like “don’t” or “O’Neill.”

---------------------------------------

### 46. Find Broken UTF-8 Sequences (Approx)
```regex
[\xC0-\xFF][^\x80-\xBF]|
[\xE0-\xEF].{0,1}|
[\xF0-\xF7].{0,2}
```
A rough way to detect malformed UTF-8 sequences.

---------------------------------------

### 47. Validate Simple IPv6 Addresses
```regex
^([0-9A-Fa-f]{1,4}:){7}[0-9A-Fa-f]{1,4}$
```
Basic IPv6 pattern (without compressed form).

---------------------------------------

### 48. Match Compressed IPv6 Addresses (Shorter Form)
```regex
^((?:[0-9A-Fa-f]{1,4}(?::[0-9A-Fa-f]{1,4})*)?)::((?:[0-9A-Fa-f]{1,4}(?::[0-9A-Fa-f]{1,4})*)?)$
```
Covers the `::` compressed notation.

---------------------------------------

### 49. Match a MAC Address
```regex
\b[0-9A-Fa-f]{2}([:\-])[0-9A-Fa-f]{2}(\1[0-9A-Fa-f]{2}){4}\b
```
Captures `XX:XX:XX:XX:XX:XX` or `XX-XX-XX-XX-XX-XX`.

---------------------------------------

### 50. Match HTML Opening and Closing Tag Pairs (Basic)
```regex
<([A-Za-z][A-Za-z0-9]*)\b[^>]*>(.*?)</\1>
```
Finds simple matching tag pairs like `<div>...</div>`.

---------------------------------------

### 51. Match Lines With Only Digits
```regex
^\d+$
```
Captures lines that contain digits only.

---------------------------------------

### 52. Match Lines With Only Letters
```regex
^[A-Za-z]+$
```
Finds lines containing letters only.

---------------------------------------

### 53. Match Lines With Only Alphanumeric Characters
```regex
^[A-Za-z0-9]+$
```
Ensures a line is purely letters and digits.

---------------------------------------

### 54. Match Lines Containing At Least One Digit
```regex
.*\d.* 
```
Captures any line that has a digit anywhere.

---------------------------------------

### 55. Match Lines Not Containing Digits
```regex
^[^0-9]*$
```
Finds lines with no digits at all.

---------------------------------------

### 56. Match Lines of a Specific Length (e.g., 8 chars)
```regex
^.{8}$
```
Captures lines exactly 8 characters long.

---------------------------------------

### 57. Remove Leading Spaces
```regex
^\s+
```
Strips any whitespace at the start of a line.

---------------------------------------

### 58. Remove Trailing Spaces
```regex
\s+$
```
Strips any whitespace at the end of a line.

---------------------------------------

### 59. Find Text Between HTML Comments
```regex
<!--(.*?)-->
```
Captures content inside `<!-- ... -->` comments.

---------------------------------------

### 60. Match “TODO” Comments
```regex
//\s*TODO:?.*
```
Finds single-line TODO comments in many languages.

---------------------------------------

### 61. Validate a Credit Card Number (Simple, 16 Digits)
```regex
^(\d{4}[-\s]?){3}\d{4}$
```
Matches 16 digits in groups of 4, optionally separated by `-` or space.

---------------------------------------

### 62. Remove `[index] =>` From PHP var_dump
```regex
\[\d+\] =>\s*
```
Strips the bracketed index lines from a PHP var_dump.

---------------------------------------

### 63. Match JSON Object Keys
```regex
"([^"]+)":\s*
```
Captures `"key": ` parts in JSON strings.

---------------------------------------

### 64. Match BBCode Tags
```regex
\[(b|i|u|url|quote)(?:=[^\]]+)?\](.*?)\[/\1\]
```
Finds basic BBCode tags like `[b]bold[/b]`, `[url=...]text[/url]`, etc.

---------------------------------------

### 65. Match Windows File Paths
```regex
[A-Za-z]:(\\[^<>:"/\\|?*]+)+
```
Locates paths like `C:\Folder\SubFolder\file.txt`.

---------------------------------------

### 66. Match Unix/Mac File Paths
```regex
/(?:[^/\0]+/)*[^/\0]+
```
Captures paths like `/usr/local/bin/script.sh`.

---------------------------------------

### 67. Match a Markdown Heading (e.g., `# Heading`)
```regex
^(#{1,6})\s+(.*)
```
Finds headings of level 1–6.

---------------------------------------

### 68. Match a YouTube Video ID in a URL
```regex
(?:youtube\.com/(?:.*v=)|youtu\.be/)([A-Za-z0-9_-]{11})
```
Captures the 11-character YouTube ID.

---------------------------------------

### 69. Match HTML Doctype Declaration
```regex
^<!DOCTYPE\s+html\s*>$
```
Locates a standard HTML5 doctype line.

---------------------------------------

### 70. Find Repetitive Punctuation
```regex
([?!.,])\1+
```
Captures sequences like `!!!` or `??`.

---------------------------------------

### 71. Match an Integer or Decimal With Optional Sign
```regex
[+-]?\d+(\.\d+)?
```
Finds positive/negative integers or decimals.

---------------------------------------

### 72. Match Lines With Balanced Quotation Marks (Approx)
```regex
^(([^"]*"){2})*[^"]*$
```
Ensures an even number of quotes in a line (approx check).

---------------------------------------

### 73. Identify Base64 Strings
```regex
([A-Za-z0-9+/]{4})*([A-Za-z0-9+/]{2}==|[A-Za-z0-9+/]{3}=)?
```
Finds typical Base64-encoded strings (no newlines).

---------------------------------------

### 74. Match a Leading “- ” (Hyphen + Space) for List Items
```regex
^-\s+
```
Captures the start of a Markdown bullet.

---------------------------------------

### 75. Match a JSON Boolean
```regex
\b(true|false)\b
```
Finds `true` or `false`.

---------------------------------------

### 76. Match a JSON Null
```regex
\bnull\b
```
Finds the keyword `null`.

---------------------------------------

### 77. Capture a CSS Class Selector
```regex
\.[A-Za-z0-9_-]+
```
Captures `.class-name` in CSS.

---------------------------------------

### 78. Capture a CSS ID Selector
```regex
#[A-Za-z0-9_-]+
```
Finds `#id-name` in CSS.

---------------------------------------

### 79. Match an Email-Like String (Loose)
```regex
[\w.-]+@[\w.-]+\.\w+
```
A less strict email pattern.

---------------------------------------

### 80. Remove All Digits
```regex
\d+
```
Deletes numeric digits.

---------------------------------------

### 81. Find Any Non-Digit
```regex
\D
```
Locates characters that are not digits.

---------------------------------------

### 82. Replace Multiple Newlines With a Single Newline
```regex
(\r?\n){2,}
```
Use with a single `\n` replacement to condense blank lines.

---------------------------------------

### 83. Detect a Potential SQL SELECT Statement
```regex
^\s*SELECT\b.*\bFROM\b
```
Basic detection for lines starting with a `SELECT ... FROM` structure.

---------------------------------------

### 84. Match an HTML-Style Closing Tag
```regex
<\/[A-Za-z][A-Za-z0-9]*\s*>
```
Locates closing tags like `</div>`.

---------------------------------------

### 85. Capture a Function Definition in Many Languages (Simplified)
```regex
function\s+([A-Za-z_]\w*)\s*\(.*\)
```
Finds `function name(...)`.

---------------------------------------

### 86. Match a Python-Style Function Definition
```regex
^\s*def\s+([A-Za-z_]\w*)\s*\(.*\):
```
Captures lines beginning with `def ...(...):`.

---------------------------------------

### 87. Remove Extra Semicolons
```regex
;{2,}
```
Replace with a single `;`.

---------------------------------------

### 88. Match a Single Quoted String With Escapes
```regex
'([^'\\]|\\.)*'
```
Captures `'some\'text'`.

---------------------------------------

### 89. Match a Double Quoted String With Escapes
```regex
"([^"\\]|\\.)*"
```
Captures `"some \"text\""`.

---------------------------------------

### 90. Strip ANSI Escape Codes
```regex
\x1B\[[0-?]*[ -/]*[@-~]
```
Removes color/control escape sequences.

---------------------------------------

### 91. Capture Email Username Part
```regex
^([^@]+)@
```
Finds the text before `@` in an email address.

---------------------------------------

### 92. Match Text Inside Curly Braces
```regex
\{([^{}]*)\}
```
Captures text within `{}`.

---------------------------------------

### 93. Match a Single or Double-Dash
```regex
-{1,2}
```
Finds `-` or `--` (useful for CLI args).

---------------------------------------

### 94. Match an XML/HTML Self-Closing Tag
```regex
<([A-Za-z][A-Za-z0-9]*)\b[^>]*\/>
```
Locates tags like `<img src="x.jpg" />`.

---------------------------------------

### 95. Capture Domain Name From an Email
```regex
@([^@\s]+)
```
Finds domain portion after `@`.

---------------------------------------

### 96. Match Only ASCII Letters
```regex
^[A-Za-z]+$
```
Ensures a string has only A–Z, ignoring digits/symbols.

---------------------------------------

### 97. Match A-F Characters (Hex Check)
```regex
^[A-Fa-f0-9]+$
```
Validates a purely hex string.

---------------------------------------

### 98. Match an HTML Color Property
```regex
color:\s*#[A-Fa-f0-9]{3,6}
```
Finds something like `color: #fff` or `color: #ffffff`.

---------------------------------------

### 99. Match an <img> Tag Source
```regex
<img\b[^>]*\bsrc\s*=\s*("[^"]*"|'[^']*')
```
Captures `src="..."` within an `img` tag.

---------------------------------------

### 100. Find <script> Tags
```regex
<script\b[^>]*>([\s\S]*?)<\/script>
```
Captures script tags and their content.

---------------------------------------

### 101. Match a Git Commit SHA (Short 7 chars)
```regex
\b[0-9a-f]{7}\b
```
Finds abbreviated commit hashes.

---------------------------------------

### 102. Match a Git Commit SHA (Full 40 chars)
```regex
\b[0-9a-f]{40}\b
```
Captures full-length commit hashes.

---------------------------------------

### 103. Match a Slack Mention
```regex
<@([A-Z0-9]+)>
```
Typical Slack user mention format.

---------------------------------------

### 104. Match an Uppercase Word
```regex
\b[A-Z]+\b
```
Finds words in ALL CAPS.

---------------------------------------

### 105. Match an Uppercase Letter Followed by Lowercase Letters
```regex
\b[A-Z][a-z]+\b
```
Captures a word with a capital first letter.

---------------------------------------

### 106. Detect an Indented Line (4 Spaces)
```regex
^( {4}).*
```
Locates lines that begin with 4 spaces.

---------------------------------------

### 107. Match an Exclamation Mark or Question Mark at End of Line
```regex
[!?]$
```
Find lines that end with `?` or `!`.

---------------------------------------

### 108. Match Lines Containing `foo` or `bar`
```regex
\b(?:foo|bar)\b
```
Captures lines containing either “foo” or “bar.”

---------------------------------------

### 109. Match Balanced Parentheses (Simple)
```regex
^\((?:[^()]|(?R))*\)$
```
A recursive pattern (PCRE) for balanced parentheses.

---------------------------------------

### 110. Find HTML Entities of Type `&#NNNN;`
```regex
&#\d+;
```
Matches numeric HTML entities like `&#160;`.

---------------------------------------

### 111. Match a Single Letter Surrounded by Spaces or Start/End
```regex
(^| )([A-Za-z])( |$)
```
Captures single-letter words.

---------------------------------------

### 112. Replace “Straight” Quotes With “Smart” Quotes (Part 1)
```regex
"([^"]+)"
```
Then replace with “$1” in some contexts.

---------------------------------------

### 113. Convert Windows Line Endings to Unix
```regex
\r\n
```
Use replacement `\n`.

---------------------------------------

### 114. Find Lines With Balanced Square Brackets (Simple)
```regex
^\[(?:[^\[\]]|(?R))*\]$
```
Recursive approach in PCRE for brackets.

---------------------------------------

### 115. Match Lines That Start With `#` (Comment in Some Files)
```regex
^#
```
Finds lines beginning with `#`.

---------------------------------------

### 116. Extract CSV Fields
```regex
([^,]+)(?:,|$)
```
Captures comma-separated values.

---------------------------------------

### 117. Match Windows Registry Path
```regex
^(HKEY_LOCAL_MACHINE|HKEY_USERS|HKEY_CURRENT_USER|HKEY_CLASSES_ROOT|HKEY_CURRENT_CONFIG)\\(.+)$
```
Locates basic registry keys.

---------------------------------------

### 118. Match an HTML Element ID Attribute
```regex
id\s*=\s*(['"])(.*?)\1
```
Finds `id="someID"` or `id='someID'`.

---------------------------------------

### 119. Capture Indented Markdown Blockquote
```regex
^>\s+(.*)
```
Find lines that begin with `>` then text.

---------------------------------------

### 120. Match “OR” in a Non-Capturing Group
```regex
(?:cat|dog|bird)
```
Find “cat,” “dog,” or “bird” without capturing.

---------------------------------------

### 121. Validate Simple Float Format
```regex
^[+-]?\d+(\.\d+)?$
```
Checks for optional sign and decimal part.

---------------------------------------

### 122. Match a Single Capital Letter
```regex
[A-Z]
```
Captures exactly one uppercase letter.

---------------------------------------

### 123. Match a Single Lowercase Letter
```regex
[a-z]
```
Captures exactly one lowercase letter.

---------------------------------------

### 124. Match a Single Alphanumeric Character
```regex
[A-Za-z0-9]
```
Captures exactly one letter or digit.

---------------------------------------

### 125. Match Whitespace Between Words
```regex
\w+\s+\w+
```
Finds pairs of words separated by whitespace.

---------------------------------------

### 126. Match Python Triple-Quoted String (Simplified)
```regex
("""|''')(.*?)\1
```
Finds triple-quoted strings, ignoring edge cases.

---------------------------------------

### 127. Match a JavaScript Arrow Function (Basic)
```regex
([A-Za-z_$][\w$]*)\s*=>\s*\{?([^}]*)\}?
```
Captures something like `foo => { ... }`.

---------------------------------------

### 128. Match a Named Capture Group (PCRE)
```regex
(?P<name>pattern)
```
Example of named capture usage.

---------------------------------------

### 129. Match Double Backslashes
```regex
\\\\
```
Captures `\\` literally.

---------------------------------------

### 130. Match a Single Backslash
```regex
\\
```
Finds a literal single backslash.

---------------------------------------

### 131. Split on Commas Not Enclosed in Quotes (Simplistic)
```regex
,(?![^"]*"(?:(?:[^"]*"){2})*[^"]*$)
```
Attempts to split CSV lines ignoring quoted commas.

---------------------------------------

### 132. Match Surrogate Pairs in Unicode
```regex
[\uD800-\uDBFF][\uDC00-\uDFFF]
```
Finds high + low surrogate pairs.

---------------------------------------

### 133. Match an Instagram Username
```regex
@([A-Za-z0-9_.]+)
```
Finds `@username` on Instagram style.

---------------------------------------

### 134. Match a JSON Number
```regex
-?\d+(?:\.\d+)?(?:[eE][+\-]?\d+)?
```
Covers integers, decimals, and scientific notation.

---------------------------------------

### 135. Match a C-Style Hex Literal
```regex
0[xX][0-9A-Fa-f]+
```
Captures `0x1A2B` etc.

---------------------------------------

### 136. Find PHP Variables
```regex
\$[A-Za-z_]\w*
```
Captures `$varName`.

---------------------------------------

### 137. Match Non-Word Boundaries
```regex
\B
```
Matches a position inside a word.

---------------------------------------

### 138. Find <style> Tags
```regex
<style\b[^>]*>([\s\S]*?)<\/style>
```
Captures CSS within `<style>`.

---------------------------------------

### 139. Match a Single CR Character
```regex
\r
```
Captures carriage return character.

---------------------------------------

### 140. Match a Single LF Character
```regex
\n
```
Locates line feed character.

---------------------------------------

### 141. Match a Time With Optional Seconds
```regex
\b([01]\d|2[0-3]):[0-5]\d(:[0-5]\d)?\b
```
Captures `HH:MM` or `HH:MM:SS`.

---------------------------------------

### 142. Find an XML/HTML Tag With Attributes
```regex
<(\w+)(\s+\w+=(?:"[^"]*"|'[^']*'))*\s*/?>
```
Basic approach to match a tag with attributes.

---------------------------------------

### 143. Match an Alphanumeric Character Repeated at Least Twice
```regex
([A-Za-z0-9])\1+
```
Find repeated letters/digits like `aa` or `222`.

---------------------------------------

### 144. Detect a Negative Decimal
```regex
^-\d+(\.\d+)?$
```
Captures strings like `-123.45`.

---------------------------------------

### 145. Remove All Vowels
```regex
[aeiouAEIOU]
```
Delete vowels from text.

---------------------------------------

### 146. Find Consecutive Word Characters of Length N (e.g., 5)
```regex
\w{5}
```
Locates sequences of 5 word chars.

---------------------------------------

### 147. Validate a Git Branch Name (Simple)
```regex
^(?!/|.*([/.]\.|\/\/|@\{|\\))[^\000-\037\177 ~^:?*[]+(?<!\.lock)(?<!/)$
```
A simplified version of Git branch name constraints.

---------------------------------------

### 148. Match a URL Path After Domain
```regex
https?:\/\/[^\/]+(\/[^?#]*)?
```
Captures optional path after a domain.

---------------------------------------

### 149. Extract Query Parameter `foo` from URL
```regex
[?&]foo=([^&#]+)
```
Finds the value of `foo=` in a query string.

---------------------------------------

### 150. Match an Empty String
```regex
^$
```
Matches lines with zero characters.

---------------------------------------

### 151. Remove CSS Comments
```regex
\/\*[^*]*\*+([^/][^*]*\*+)*\/
```
Strips `/* ... */` blocks in CSS.

---------------------------------------

### 152. Match Balanced Quotes in a String (Quoted Pairs)
```regex
"((?:\\.|[^"\\])*)"
```
Captures string content allowing for escapes.

---------------------------------------

### 153. Find Strings “foo_bar” Where `foo` and `bar` Are Alphadigits
```regex
^[A-Za-z0-9]+_[A-Za-z0-9]+$
```
Captures patterns like `abc_123`.

---------------------------------------

### 154. Match an Optional Sign Followed by Digits
```regex
^[+-]?\d+$
```
Captures integers with optional + or -.

---------------------------------------

### 155. Match a Word at the Start of a Line
```regex
^\w+
```
Locates a word at the beginning of each line.

---------------------------------------

### 156. Match a Word at the End of a Line
```regex
\w+$
```
Finds a word at the end of each line.

---------------------------------------

### 157. Match `<a href="...">` Tags
```regex
<a\s+href\s*=\s*(['"])(.*?)\1
```
Captures link references from anchor tags.

---------------------------------------

### 158. Match a Word in the Middle of a Line
```regex
(?<!^)\b\w+\b(?!$)
```
Finds a word not at start or end of line (lookbehind/lookahead).

---------------------------------------

### 159. Find Comments in INI Files
```regex
^[ \t]*;.*$
```
Captures lines starting with optional spaces and `;`.

---------------------------------------

### 160. Validate Basic HTML5 Tag Name
```regex
<\/?[A-Za-z][A-Za-z0-9-]*\b[^>]*>
```
Matches opening or closing tags like `<my-tag>`.

---------------------------------------

### 161. Match Surrounded by Parentheses or Brackets (Either/Or)
```regex
(\(|\[)(.*?)(\)|\])
```
Captures text in either `( )` or `[ ]`.

---------------------------------------

### 162. Replace HTML `<br>` with Newlines
```regex
<br\s*\/?>
```
Use replacement `\n` or similar.

---------------------------------------

### 163. Find Lines Containing Only Punctuation
```regex
^[^\w\s]+$
```
Captures lines of purely non-word, non-space characters.

---------------------------------------

### 164. Detect an HTML Self-Closing Tag Like `<br/>`
```regex
<\w+\s*/>
```
Simple approach for self-closing tags.

---------------------------------------

### 165. Find Mustache-Style Templates
```regex
\{\{\s*[\w.]+\s*\}\}
```
Locates `{{ variable }}` tokens.

---------------------------------------

### 166. Match Non-ASCII Characters (Alternate)
```regex
[^\u0000-\u007F]
```
Captures extended Unicode.

---------------------------------------

### 167. Match IP-Like Strings (Loose)
```regex
\d+\.\d+\.\d+\.\d+
```
A simpler IP pattern (not range-validated).

---------------------------------------

### 168. Match a Word Boundary
```regex
\b
```
A zero-width boundary between word char and non-word char.

---------------------------------------

### 169. Identify HTML `<meta>` Tags
```regex
<meta\b[^>]*>
```
Finds meta tags.

---------------------------------------

### 170. Find Incomplete HTML Tags (No Closing ‘>’)
```regex
<[^>]*$
```
Captures lines where a tag was never closed.

---------------------------------------

### 171. Match a Literal Dollar Sign
```regex
\$
```
Escaped dollar sign.

---------------------------------------

### 172. Match Potential Domain (No Protocol)
```regex
(?:[a-zA-Z0-9-]+\.)+[a-zA-Z]{2,}
```
Finds something like `example.com`.

---------------------------------------

### 173. Identify Duplicate Consecutive Lines (Using Backreferences)
```regex
^(.*)(\r?\n\1)+$
```
With the proper replacement, you can keep only one.

---------------------------------------

### 174. Match C++-Style Single-Line Comment
```regex
\/\/.*
```
Captures `// comment` lines.

---------------------------------------

### 175. Match Lines With a Number Then a Word
```regex
^\d+\s+\w+
```
Find lines like `123 apple`.

---------------------------------------

### 176. Capture a Balanced Quoted Section
```regex
"([^"\\]*(\\.[^"\\]*)*)"
```
Handles escape sequences inside quotes.

---------------------------------------

### 177. Remove All Non-Word and Non-Space Characters
```regex
[^\w\s]+
```
Strips punctuation except underscores.

---------------------------------------

### 178. Match HTML <head> Tag Content (Rough)
```regex
<head\b[^>]*>([\s\S]*?)<\/head>
```
Captures everything inside `<head>`.

---------------------------------------

### 179. Identify Email-Like Strings Without TLD Checking
```regex
[^@\s]+@[^@\s]+
```
Anything@anything not containing spaces.

---------------------------------------

### 180. Capture Text After Last Slash in a URL
```regex
[^/]+$
```
Finds the final segment of a path.

---------------------------------------

### 181. Match a Word Followed by a Colon
```regex
\b\w+:
```
Finds tokens like `Label:`.

---------------------------------------

### 182. Delete Everything After a `#` in a Line (Like a Comment)
```regex
#.*$
```
Removes “# comment to end of line.”

---------------------------------------

### 183. Grab a Time Format (HH:MM 12-hour with Optional AM/PM)
```regex
\b(0?[1-9]|1[0-2]):[0-5]\d(?:\s?[APMapm]{2})?\b
```
Optional AM/PM.

---------------------------------------

### 184. Find Repeated Patterns of 2 Characters
```regex
(.{2})\1+
```
Captures consecutive duplicates of 2-character blocks.

---------------------------------------

### 185. Detect HTML Entities of Type `&...;`
```regex
&[^;\s]+;
```
Captures any `& ... ;` entity.

---------------------------------------

### 186. Match a Negative Lookbehind (No “foo” Before)
```regex
(?<!foo)bar
```
Find `bar` not preceded by `foo`.

---------------------------------------

### 187. Remove `console.log( ... );` Lines
```regex
^\s*console\.log\(.*\);\s*$
```
Deletes JavaScript debug logs.

---------------------------------------

### 188. Match a Simple Balanced Tag Pair With Optionally Nested Content
```regex
<(\w+)(?:"[^"]*"|'[^']*'|[^'">])*>(?:(?R)|[^<])*<\/\1>
```
Recursive pattern for nested tags (PCRE).

---------------------------------------

### 189. Match DOS/Windows Drive Letter
```regex
^[A-Za-z]:\\
```
Captures `C:\` at start of line.

---------------------------------------

### 190. Match UNIX Hidden Files (Starting With Dot)
```regex
^\.[^/]+
```
Finds `.filename`.

---------------------------------------

### 191. Extract Version Number `major.minor.patch` 
```regex
(\d+)\.(\d+)\.(\d+)
```
Captures version triple.

---------------------------------------

### 192. Capture a JSON String Value
```regex
"([^"\\]*(\\.[^"\\]*)*)"
```
Inside double quotes, allowing escapes.

---------------------------------------

### 193. Match Balanced Angle Brackets (Rough)
```regex
^<((?:[^<>]|(?R))*)>$
```
Recursive approach for `< >` pairs.

---------------------------------------

### 194. Find Classes in Java Code
```regex
\bclass\s+([A-Za-z_]\w*)
```
Captures class name after `class`.

---------------------------------------

### 195. Find or Validate a Swift `let` Declaration
```regex
^\s*let\s+([A-Za-z_]\w*).*
```
Captures variable name after Swift `let`.

---------------------------------------

### 196. Capture Ruby Symbol Names
```regex
:([A-Za-z_]\w*)
```
Finds `:symbol`.

---------------------------------------

### 197. Match HTML Title Tag
```regex
<title\b[^>]*>([\s\S]*?)<\/title>
```
Captures the text inside `<title>`.

---------------------------------------

### 198. Find Comments in Shell Scripts
```regex
^\s*#.*$
```
Captures `# comment` lines in shell.

---------------------------------------

### 199. Match Strings With No Spaces
```regex
^[^\s]+$
```
Ensures no whitespace in the entire string.

---------------------------------------

### 200. Match a Markdown Link Title (After a Link)
```regex
\[([^\]]+)\]\(([^)]+)\)
```
Captures `[text](URL)` in Markdown.

---------------------------------------

### 201. Match a CSV Row (Basic Quoted Fields)
```regex
"[^"]*"|[^,]+
```
Captures either quoted fields or unquoted chunks split by commas.

---

### 202. Find a Triple-Backtick Markdown Code Block
```regex
``` + `([\s\S]*?)` + ```
```
Captures text wrapped in ```triple backticks```. (Adjust to your environment’s escaping rules.)

---

### 203. Match an IP Address With Optional Port
```regex
\b((25[0-5]|2[0-4]\d|[01]?\d?\d)\.){3}(25[0-5]|2[0-4]\d|[01]?\d?\d)(:\d{1,5})?\b
```
Captures IPv4 and optional port (e.g., `123.45.67.89:8080`).

---

### 204. Find Lines *Not* Containing “foo”
```regex
^(?!.*foo).*$
```
Negative lookahead ensures “foo” isn’t in the line.

---

### 205. Capture Duplicate Adjacent Lines (Ignoring Case)
```regex
(?i)^(.*)(\r?\n\1)+$
```
In some editors, replace with `\1` to keep single instance.

---

### 206. Find 3+ Consecutive Uppercase Letters
```regex
[A-Z]{3,}
```
Captures sequences like `ABC` or `XYZPQ`.

---

### 207. Identify Text in Backticks
```regex
`([^`]+)`
```
Finds substrings between single backticks.

---

### 208. Match Line Starting With Digits and Ending With “?”
```regex
^[0-9].*\?$
```
Start with a digit, end with question mark.

---

### 209. Match Shell Variable References `$VAR` or `${VAR}`
```regex
\$(?:[A-Za-z_]\w*|\{[A-Za-z_]\w*\})
```
Finds `$NAME` or `${NAME}` usage in shell scripts.

---

### 210. Capture Repeated Adjacent Words Ignoring Punctuation
```regex
\b([A-Za-z]+)\W+\1\b
```
Find “foo, foo” or “bar - bar.”

---

### 211. Lines in ALL CAPS but Containing at Least One Digit
```regex
^[A-Z0-9]*[0-9][A-Z0-9]*$
```
Only uppercase letters and digits, must have at least one digit.

---

### 212. Remove HTML `<span>` Tags (Any Attributes)
```regex
<\/?span\b[^>]*>
```
Matches opening or closing `<span ...>` tags for removal.

---

### 213. Find Self-Closing HTML Tags with No Inner Content
```regex
<\w+\b[^>]*\/>
```
Captures standalone tags like `<br/>`, `<img/>` (any tag name).

---

### 214. Match Doxygen Comment Block
```regex
\/\*\*[\s\S]*?\*\/
```
Captures `/** ... */` blocks in code.

---

### 215. Capture Entire String Except the Last Character
```regex
^(.).*(?=.) 
```
Use capturing groups carefully in certain editors. Or simpler: `^(.*).$`.

---

### 216. Match a Line of Only Underscores
```regex
^_+$
```
Captures lines solely containing `_`.

---

### 217. 3+ Consecutive Punctuation Marks
```regex
[!-/:-@[-`{-~]{3,}
```
Find runs of punctuation, 3 or more in length.

---

### 218. Capture Text in SQL `--` Comment
```regex
--(.*)$
```
Captures the remainder of the line after `--`.

---

### 219. Match IPv4 With Potential Leading Zeros
```regex
\b(\d{1,3}\.){3}\d{1,3}\b
```
Loose pattern allowing `010.001.50.000`.

---

### 220. Lines With a Digit Repeated Exactly 4 Times
```regex
^.*(\b(\d)\2{3}\b).*$
```
Captures lines with a quadruple digit like `1111`.

---

### 221. Remove All Parentheses
```regex
[()]+
```
Deletes both opening and closing parentheses.

---

### 222. Lines Ending With “;” and No Leading Spaces
```regex
^[^ ].*;$
```
Captures lines that do not start with a space and end with semicolon.

---

### 223. Capture Domain (With Optional Subdomains, No Protocol)
```regex
((?:[A-Za-z0-9-]+\.)+[A-Za-z]{2,})
```
Grabs something like `sub.example.co.uk`.

---

### 224. Optional Sign, Up to 3 Digits, Optional Decimal
```regex
^[+-]?\d{1,3}(\.\d+)?$
```
Covers small numeric values like `+12.34`.

---

### 225. Match a Phrase Repeated at Least Twice
```regex
(\b\w+\b).*\1
```
Captures any word repeated later in the same line.

---

### 226. Consecutive Words Differing Only by Case
```regex
\b([A-Za-z]+)\s+\1\b(?-i)
```
Use case-insensitive matching in some engines; detect “Hello hello”.

---

### 227. Match a Word Not Containing 'e'
```regex
\b[a-df-zA-DF-Z]+\b
```
Captures words lacking letter e/E.

---

### 228. Lines Where the Last Character is a Digit
```regex
\d$
```
Simple check for trailing digit.

---

### 229. Match a Multiline String (Dot Matching Newlines)
```regex
(?s)(^.*$)
```
Use `(?s)` or equivalent to let `.` span multiple lines.

---

### 230. Lines Starting With a Letter, Containing No Digits
```regex
^[A-Za-z][A-Za-z\s\W]*$
```
No digits at all, but starts with letter.

---

### 231. Remove Inline CSS `style="..."`
```regex
style\s*=\s*(['"])[\s\S]*?\1
```
Finds the `style=` attribute for removal.

---

### 232. Find Repeated Capturing Groups Like `(abcabc...)`
```regex
^([A-Za-z]+)\1+$
```
Matches repeated pattern (e.g., “abcabc”).

---

### 233. Identify Format Specifiers `%1, %2, ...`
```regex
%\d+
```
Locates placeholders like `%1` in some templating contexts.

---

### 234. Match a Multiline `.env` Assignment (e.g., `VAR=value`)
```regex
^([A-Za-z_]\w*)=(.*)$
```
Captures variable name and value in .env files.

---

### 235. Lines With Only Digits or Punctuation (No Letters)
```regex
^[\d\p{P}\p{S}]*$
```
Find digits and punctuation/symbols only.

---

### 236. Match a Java `import` Statement
```regex
^\s*import\s+[\w.]+\s*;\s*$
```
Captures standard `import` lines in Java.

---

### 237. Find a `printf` Call in C (Basic)
```regex
printf\s*\(\s*".*?"\s*(?:,\s*.*?)*\);
```
Matches `printf("some format", args...);`.

---

### 238. Match a Simple `YYYY-MM-DD` Date
```regex
\b\d{4}-\d{2}-\d{2}\b
```
Captures, e.g., `2025-03-12`.

---

### 239. Uppercase Acronym Followed by Parentheses
```regex
\b([A-Z]+)\(([^)]*)\)
```
Example: `HTML(Document)`.

---

### 240. Match a Forward Slash Not Preceded by Backslash
```regex
(?<!\\)\/
```
Negative lookbehind for `\`.

---

### 241. Lines With Curly Braces but No Content
```regex
\{\s*\}
```
Captures `{}` with only optional whitespace inside.

---

### 242. Find Duplicate Lines Ignoring Leading/Trailing Whitespace
```regex
^\s*(.*?)(\s*)$[\r?\n]+\s*\1\2$
```
Tricky usage with certain editors to unify duplicates.

---

### 243. Match Lines Ending With a Colon
```regex
.*:\s*$
```
Any line finishing with “:”.

---

### 244. Capture Digits Within Alphabetic Text
```regex
([A-Za-z]+)(\d+)([A-Za-z]+)
```
Example: “abc123def.”

---

### 245. Lines Starting With Multiple `#` (Markdown Heading)
```regex
^#{2,}\s+
```
Captures `##`, `###`, etc.

---

### 246. Entire Line Is One Single Word (Ignoring Punctuation)
```regex
^[A-Za-z]+[.!?']?$
```
For example, `Hello`, `Hello!`.

---

### 247. Remove `javascript:` Prefix in URLs
```regex
^(?:javascript:)(.*)$
```
Replace with `$1`.

---

### 248. Numeric Strings Containing Period or Comma
```regex
^\d*[\.,]\d+$
```
Matches e.g. `1,234` or `12.34`.

---

### 249. Lines With Exactly Two Words Separated by a Single Space
```regex
^[^\s]+ [^\s]+$
```
Captures lines with `word1 word2` only.

---

### 250. Capture Text in Triple Braces `{{{...}}}`
```regex
\{\{\{([\s\S]*?)\}\}\}
```
Locates `{{{ foo }}}`.

---

### 251. Phone Number With Optional Extension
```regex
\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}(?:\s*(?:x|ext)\s*\d+)? 
```
Example: `123-456-7890 x123`.

---

### 252. Lines Containing Only Letters or Punctuation
```regex
^[A-Za-z\p{P}\p{S}]+$
```
No digits, no whitespace.

---

### 253. Lines of Odd Number of Characters
```regex
^(?:.{2})*.$
```
Ensures line length is odd.

---

### 254. Text Inside Square Brackets (No Nesting, Rough)
```regex
\[[^\[\]]*\]
```
Find `[...]` ignoring nesting.

---

### 255. Contains “hello” Regardless of Case
```regex
(?i)hello
```
Case-insensitive match for “hello.”

---

### 256. Integer With Thousands Separators (Naive)
```regex
^\d{1,3}(,\d{3})*$
```
Example: `1,234,567`.

---

### 257. Lines With Exactly One Comma
```regex
^[^,]*,[^,]*$
```
No second comma present.

---

### 258. Lines With No Vowels at All
```regex
^[^aeiouAEIOU]*$
```
Captures lines devoid of vowels.

---

### 259. Negative Lookahead for “test” at Start
```regex
^(?!test)
```
Ensure line does not start with “test.”

---

### 260. Lines That Aren’t Blank or Whitespace Only
```regex
^(?!\s*$).+
```
Excludes empty lines.

---

### 261. Capture Triple Letter Repeats
```regex
([A-Za-z]{3})\1*
```
E.g. “abcabcabc.”

---

### 262. Remove `<hr>` or `<hr/>` Tags
```regex
<hr\s*/?>
```
Strips horizontal rule elements.

---

### 263. CSS Property With Hyphen (e.g., `font-size`)
```regex
[a-zA-Z-]+\s*:\s*[^;]+;
```
Find lines like `font-size: 14px;`.

---

### 264. Lines Containing `<` or `>` but Not Quotes
```regex
<[^">]*> 
```
Roughly captures tags ignoring attributes with quotes.

---

### 265. Markdown Code Block With Language
```regex
```([a-zA-Z]+)\n([\s\S]*?)\n```
```
Captures language after triple backticks.

---

### 266. Capture Variable Assignments (`var = value`)
```regex
^([A-Za-z_]\w*)\s*=\s*(.*)$
```
Spaces optional.

---

### 267. Repeated Words Ignoring Punctuation
```regex
\b([A-Za-z]+)\W+\1\b
```
Like “yes, yes.”

---

### 268. Lines With Parentheses but No Brackets
```regex
^(?=.*\().*(?!.*\[).*$
```
Lookaheads ensure a "(" is present, "[" absent.

---

### 269. Uppercase Letter Followed by Exactly 3 Digits
```regex
[A-Z]\d{3}
```
E.g. `A123`.

---

### 270. Rough Capture of HTML Attributes
```regex
(\w+)\s*=\s*(["'])(.*?)\2
```
Finds name="value".

---

### 271. Simplistic XML Attribute (Ignoring Quotes)
```regex
\b\w+\s*=\s*\S+
```
Capture `attr=value` ignoring quotes.

---

### 272. Numeric Ranges Like `1-5` or `10-20`
```regex
\b\d+\s*-\s*\d+\b
```
Range with hyphen.

---

### 273. Shell Variable in Curly Braces `$\{VAR\}`
```regex
\$\{[A-Za-z_]\w*\}
```
Finds references like `${PATH}`.

---

### 274. Capture the Nth Word (e.g., 3rd Word)
```regex
^(?:\S+\s+){2}(\S+)
```
Grabs the 3rd word. Adjust the count.

---

### 275. Lines With More Than One `!`
```regex
^.*!.*!.*$
```
At least two exclamation marks.

---

### 276. Match Triple Dashes
```regex
^-{3}$
```
Captures lines of exactly three dashes (like `---`).

---

### 277. Repeated Punctuation Sequences
```regex
([!-/:-@[-`{-~])\1+
```
Captures punctuation repeated 2+ times.

---

### 278. Email Addresses *Not* Ending in `.com`
```regex
[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.(?!com)[a-zA-Z]{2,}
```
Excludes `.com` TLD.

---

### 279. Lines With Uppercase Letters and Underscores
```regex
^(?=.*[A-Z])(?=.*_).+$
```
Lookahead ensures both uppercase and `_`.

---

### 280. Lines Longer Than 80 Characters
```regex
^.{81,}$
```
Captures lines over 80 chars.

---

### 281. Lines Not Preceded By a Space (Lookbehind)
```regex
(?<! )^.*
```
In some engines, ensures no space before line start (context-sensitive usage).

---

### 282. Capture Text After the Second Comma
```regex
^[^,]*,[^,]*,(.*)$
```
Group 1 is everything post-second comma.

---

### 283. Entirely Numeric Except One Dash
```regex
^\d*-?\d*$
```
E.g. `123-456` or `123456`.

---

### 284. Lines Containing Tabs but No Spaces
```regex
^\t+[^\s]*$
```
Adjust as needed if more text is allowed.

---

### 285. Match Exactly 9 Digits (Possible SSN)
```regex
^\d{9}$
```
Captures 9-digit strings (not validated).

---

### 286. Base32 Encoded Strings (Rudimentary)
```regex
^[A-Z2-7]+=*$
```
A simplistic approach for base32 blocks.

---

### 287. Multiline Enclosed by Parentheses (No Nesting)
```regex
\([^()]*\)
```
Captures `(...)` ignoring nested parentheses.

---

### 288. Lines With Digits/Punctuation but No Letters
```regex
^[0-9\p{P}\p{S}]+$
```
Ensures no letters appear.

---

### 289. Consecutive Capital Letters Not Preceded by Space
```regex
(?<! )([A-Z]{2,})
```
Find capital letter blocks ignoring a preceding space.

---

### 290. Lines With Exactly 3 Words
```regex
^(\S+\s+){2}\S+$
```
No more, no less than three whitespace-delimited items.

---

### 291. JSP `<%@ taglib` Directive
```regex
<%@\s*taglib\s+[^%]*%>
```
Captures lines referencing a JSP tag library.

---

### 292. Starts With Capital, Ends With Period (Ignoring Trailing Spaces)
```regex
^[A-Z].*\.\s*$
```
Line must begin uppercase, end with a period.

---

### 293. Semantic Version With Optional Build
```regex
\b\d+\.\d+\.\d+(?:\+[0-9A-Za-z.-]+)?\b
```
E.g. `1.2.3+build.123`.

---

### 294. Dockerfile `ENV VAR=value`
```regex
^ENV\s+([A-Za-z_]\w*)=(.*)$
```
Captures variable assignments in Dockerfiles.

---

### 295. Lines With Exactly Two Digits Total
```regex
^(?:[^0-9]*[0-9][^0-9]*[0-9][^0-9]*)$
```
No more than two digits anywhere in the line.

---

### 296. Lines With Only Letters and Digits (No Punctuation)
```regex
^[A-Za-z0-9]+$
```
Pure alphanumeric lines.

---

### 297. User Mentions Like `@user:` at Start
```regex
^@([A-Za-z0-9_]+):
```
Captures handle right after `@`.

---

### 298. Lines With `{...}` That Contain a Colon Inside
```regex
\{\s*[^{}]*:\s*[^{}]*\}
```
E.g. `{ key: value }`.

---

### 299. Match a Single Space or Tab, But Not Multiple
```regex
[ \t](?![ \t])
```
One whitespace char not followed by another.

---

### 300. Lines With `/*` But No Closing `*/`
```regex
/\*[^*]*(\*+[^/][^*]*)*$
```
Incomplete comment lines.

---

### 301. Text Between Single Curly Braces (No Nesting)
```regex
\{[^{}]*\}
```
Captures `{some text}`.

---

### 302. Lines With `/` but Not `//`
```regex
^(?!.*\/\/).*\/.*$
```
Ensures slash is present but `//` is absent.

---

### 303. Only Hex Digits, Longer Than 6
```regex
^[A-Fa-f0-9]{7,}$
```
7 or more hex characters.

---

### 304. Simple C# Lambda `(int x) => x * 2`
```regex
\(\s*[A-Za-z_]\w*\s+[A-Za-z_]\w*\s*\)\s*=>\s*[^;]+;
```
Captures typed lambda expression.

---

### 305. Capture `WHERE` Clause in SQL (Ignoring Newlines)
```regex
WHERE\s+([\s\S]*?)(?=\bGROUP\b|\bORDER\b|$)
```
Extracts the text until next keyword or EOF.

---

### 306. Lines Containing Odd Number of Digits
```regex
^(?:.*\d.*\d.*)*.*\d?$ 
```
Trick to ensure odd count of digits.

---

### 307. Strictly Increasing Digit Sequence
```regex
^(?=1234|(?=(\d)\1<\2).*).+$
```
Full pattern is tricky; simpler approximate:
```regex
^(?:(0(?![01])|1(?!2)|2(?!3)|3(?!4)|4(?!5)|5(?!6)|6(?!7)|7(?!8)|8(?!9)|9(?!$)))+$
```
(A bit contrived. Real regex might be more engine-specific.)

---

### 308. Duplicate Lines Ignoring Case
```regex
(?i)^(.*)(\r?\n\1)+$
```
Case-insensitive duplicates.

---

### 309. Lines With `(` But Missing `)`
```regex
^(?=.*\().*(?!.*\)).*$
```
Lookaheads to check for `(` present, `)` absent.

---

### 310. Phone Number With Country Code `+1 123-456-7890`
```regex
^\+\d+\s+\d{3}[-.\s]?\d{3}[-.\s]?\d{4}$
```
Basic pattern for a plus-coded phone.

---

### 311. Substring Starting “abcd” and Ending “efgh” (Dot Matches Newlines)
```regex
(?s)abcd.*?efgh
```
Captures across multiple lines if needed.

---

### 312. Mostly Digits but Exactly One Letter
```regex
^[0-9]*[A-Za-z][0-9]*$
```
One letter among digits.

---

### 313. Date Format `DD Mon YYYY` (Loose)
```regex
\b\d{1,2}\s+(Jan|Feb|Mar|Apr|May|Jun|Jul|Aug|Sep|Oct|Nov|Dec)\s+\d{4}\b
```
Example: `01 Jan 2020`.

---

### 314. Lines Containing “foo” Exactly Twice
```regex
^(?:[^f]*f(?!oo)|f(?!oo)|o(?!o)|[^fo])*foo(?:[^f]*f(?!oo)|f(?!oo)|o(?!o)|[^fo])*foo(?:[^f]*f(?!oo)|f(?!oo)|o(?!o)|[^fo])*$ 
```
A big pattern, or simpler with capturing:
```regex
^(?:.*foo){2}.*(foo).*$  # Then verify count in some editors
```
(Workarounds vary by tool.)

---

### 315. Repeated Words With Punctuation in Between
```regex
\b([A-Za-z]+)\W+\1\b
```
Like “hello—hello” or “yes, yes.”

---

### 316. CSV Lines With at Least 4 Commas
```regex
^(?:[^,]*,){4,}[^,]*$
```
At least five fields total.

---

### 317. Lines With Nested Parentheses `(()())` (Approx PCRE)
```regex
^\((?:[^()]+|(?R))*\)$
```
Recursive approach to check nesting.

---

### 318. reStructuredText Heading Style
```regex
^(.*)\r?\n=+\s*$
```
Line followed by line of `=`. Captures heading text.

---

### 319. Lines With a Single Quote but No Double Quotes
```regex
^(?=.*')(?!.*").*$
```
Lookahead ensures `'` present, `"` absent.

---

### 320. Lines of Only Prime Digits (2,3,5,7)
```regex
^[2357]+$
```
Digits restricted to prime digits.

---

### 321. Numeric Fractions Like `num/num`
```regex
\b\d+/\d+\b
```
E.g. `3/4`.

---

### 322. `TODO` in UPPERCASE Only
```regex
\bTODO\b
```
Ensures exact uppercase match.

---

### 323. Capture C-Style Multiline `/* ... */` Comments
```regex
\/\*([\s\S]*?)\*\/
```
Includes newlines.

---

### 324. Lines With `\d-\d` But Not a Full Phone
```regex
\b\d+-\d+\b
```
E.g. `123-45`.

---

### 325. Full Floating-Point With Optional Exponent (Ignoring Leading/Trailing Spaces)
```regex
^\s*[+-]?\d+(\.\d+)?([eE][+-]?\d+)?\s*$
```
Captures float with exponent.

---

### 326. Balanced Curly Braces (Naive)
```regex
^\{[^{}]*(\{[^{}]*\}[^{}]*)*\}$
```
Non-recursive approximation.

---

### 327. Multiple Colons but No Semicolons
```regex
^(?=.*:.*:)(?!.*;).*$
```
At least 2 colons, zero semicolons.

---

### 328. Start With 3 Identical Digits
```regex
^(\d)\1\1.*$
```
Three repeated digits at line start.

---

### 329. Repeated Sequences of Letters Ignoring Underscores
```regex
([A-Za-z]+)(?:_+\1)+
```
E.g. `abc_abc_abc`.

---

### 330. End With Digit Repeated 3+ Times
```regex
\d\1\1+$
```
Look for “(\d)\1\1+” at line end.

---

### 331. Lines With Pattern Like `word:word:word`
```regex
^\w+:\w+:\w+$
```
Exactly three groups separated by colons.

---

### 332. Match `{{domain}}` Placeholders
```regex
\{\{[A-Za-z0-9_-]+\}\}
```
Find templated placeholders.

---

### 333. Lines With Backslashes but No Forward Slashes
```regex
^(?=.*\\)(?!.*\/).*$
```
Lookahead ensures `\` present, `/` absent.

---

### 334. `<img>` Tag Missing `alt`
```regex
<img\b((?!alt=)[^>])*> 
```
Doesn’t strictly check for other attributes, but excludes `alt`.

---

### 335. Repeated Word Separated by a Comma: `word,word`
```regex
\b(\w+),\1\b
```
Like `apple,apple`.

---

### 336. Lines Starting With One or More Tabs
```regex
^\t+
```
Captures lines that begin with tabs.

---

### 337. Numeric Pair `x/y` Anywhere
```regex
\b(\d+)\/(\d+)\b
```
Groups for both numbers.

---

### 338. Incomplete HTML Comment `<!--` Not Followed by `-->`
```regex
<!--(?!.*-->)
```
Captures lines with `<!--` but missing closing.

---

### 339. Lines With More Digits Than Letters
```regex
^(?=(?:.*\d){2,})(?=(?:.*[A-Za-z])*)(?{some logic?})$
```
A direct count comparison is tricky. Approx approach:
```regex
^(?:[^A-Za-z]*\d[^A-Za-z]*){n,} 
```
One might need scripting logic. Concept example.

---

### 340. Exactly 2 Uppercase Letters in the Line
```regex
^[^A-Z]*[A-Z][^A-Z]*[A-Z][^A-Z]*$
```
No more than 2 uppercase chars total.

---

### 341. Lines Starting With `export ` (Shell)
```regex
^export\s+\w+
```
Captures environment exports.

---

### 342. Python f-String with Placeholder
```regex
f"(?:\\.|[^"\\])*{[^}]+}(?:\\.|[^"\\])*"
```
Roughly captures an f-string with a curly expression.

---

### 343. Repeated Letter Ignoring Case (e.g., “A” next to “a”)
```regex
(?i)([a-z])\1
```
Case-insensitive detection of adjacent letter repeats.

---

### 344. Duplicate Lines Ignoring Punctuation
```regex
^[[:punct:]\s]*(.*?)[[:punct:]\s]*$[\r?\n]+^[[:punct:]\s]*\1[[:punct:]\s]*$
```
In certain editors, use capturing groups carefully.

---

### 345. Expression in Parentheses Followed by a Colon
```regex
\([^)]*\):
```
Matches `(anything):`.

---

### 346. Decimal Number With Exactly 2 Decimal Places
```regex
^\d+(\.\d{2})?$
```
E.g. `123.45`.

---

### 347. URL With Query but No Fragment
```regex
https?:\/\/[^#?]+(\?[^#]+)$
```
Must have `?`, must not have `#`.

---

### 348. Lines Ending With a Slash (Ignoring Trailing Spaces)
```regex
\/\s*$
```
Slash followed by optional whitespace.

---

### 349. Markdown Link Format: `[Text](URL)` Incomplete?
```regex
^\[([^\]]+)\]\(([^)]+)\)$
```
Captures entire line as a link.

---

### 350. Lines With More Punctuation Than Letters
```regex
^(?=(?:.*[!-/:-@[-`{-~]){n,})(?=(?:.*[A-Za-z]){m,}).*$
```
---

### 351. Match a Simple JSON Array of Strings
```regex
\[\s*"[^"]*"(?:\s*,\s*"[^"]*")*\s*\]
```
Captures `["one","two","three"]`, ignoring nested arrays.

---

### 352. Match a Bareword Followed by Curly-Brace Block (like in many config languages)
```regex
^[A-Za-z_][A-Za-z0-9_]*\s*\{[^{}]*\}$
```
Find lines such as `block { ... }` (single-line only).

---

### 353. Find Trailing “.com” Domain in Text
```regex
[a-zA-Z0-9-]+\.(?:com)\b
```
Matches a string that ends in `.com`.

---

### 354. Match a Dart/Flutter `import 'package:...'` Statement
```regex
^\s*import\s+'package:[^']+';\s*$
```
Captures a typical Dart package import line.

---

### 355. Lines With `=` But No `==` (Assignment vs Comparison)
```regex
^(?=.*=)(?!.*==).*$
```
Ensures `=` is present but double-equals is absent.

---

### 356. Text Surrounded by «angle quotes»
```regex
«([^»]+)»
```
Finds content within `« ... »`.

---

### 357. Match Single Word in Square Brackets at Start of Line
```regex
^\[([A-Za-z0-9_]+)\]
```
Captures `[Section]` format at line start.

---

### 358. Lines With Even Number of Words
```regex
^(\S+\s+\S+\s+)*\S+\s*\S*$ 
```
Tricky approach: pairs of words repeated. Exact logic can vary by engine.

---

### 359. Capture Non-Greedy Until a Slash
```regex
^([^/]+)/?
```
Captures everything until the first `/`, optionally including it.

---

### 360. Matching a 2D Array Notation, e.g. `[[1,2],[3,4]]`
```regex
\[\[(?:\d+(?:,\d+)*)?(?:\]\s*,\s*\[(?:\d+(?:,\d+)*)?)*\]\]
```
Finds nested bracket pairs with digits inside.

---

### 361. Lines Containing Two Uppercase Words
```regex
^(?=.*\b[A-Z]+\b.*\b[A-Z]+\b).+$
```
At least two all-uppercase words in a line.

---

### 362. Match a Python-Style Decorator
```regex
^@\w+(?:\.\w+)*\s*$
```
Captures lines like `@decorator` or `@module.decorator`.

---

### 363. Find HTML `<p>` Tag *Not* Containing `class` Attribute
```regex
<p(?![^>]*\bclass\b)[^>]*>
```
Negative lookahead ensures `class` attribute is missing.

---

### 364. Capture a Windows Shortcut `.lnk` Filename
```regex
^[^\\/:*?"<>|]+\.lnk$
```
Simple check for filename ending `.lnk`.

---

### 365. Lines That Are Comments in SQL (`-- ...`) but Not `/* ... */`
```regex
^\s*--(?!.*\/\*).*$
```
Ensures `--` present, excludes `/*`.

---

### 366. Catch a Basic Fortran Label (Up to 5 digits in cols 1-5)
```regex
^(\d{1,5})\s
```
Legacy Fortran style. (Editor column-based context might differ.)

---

### 367. Match a COBOL ENVIRONMENT DIVISION Line
```regex
^\s*ENVIRONMENT\s+DIVISION\.\s*$
```
Very specific to COBOL source.

---

### 368. Find Lines With MD5 Hash Preceding a Filename
```regex
^[a-fA-F0-9]{32}\s+.+$
```
Like checksums used in file listings.

---

### 369. Validate a Simple UK Postcode (Loose)
```regex
^[A-Z]{1,2}\d[A-Z\d]?\s*\d[ABD-HJLNP-UW-Z]{2}$
```
A rough check, ignoring all nuances.

---

### 370. YAML Key-Value Pair (Basic)
```regex
^([A-Za-z0-9_-]+):\s*(.*)$
```
Captures “key: value” in YAML.

---

### 371. Lines With Balanced Single Quotes (Even Count)
```regex
^([^']*'[^']*'){0,}[^']*$
```
Ensures quotes appear in pairs on a single line (approx).

---

### 372. Find IPv4 Mapped IPv6 Addresses
```regex
::ffff:(\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3})
```
Covers the `::ffff:192.168.0.1` pattern.

---

### 373. Lines Starting and Ending With the Same Punctuation
```regex
^([!-/:-@[-`{-~])[\s\S]*\1$
```
Captures a single punctuation char at start/end of line.

---

### 374. Regex for a Nix-like Shebang: `#!/usr/bin/env xyz`
```regex
^#!\/usr\/bin\/env\s+\S+
```
Finds shebang lines pointing to env.

---

### 375. Lines That Are Exactly One Quoted String
```regex
^"([^"\\]|\\.)*"?$
```
No extra text around it.

---

### 376. Extract Comments in `.properties` Files (`# comment`)
```regex
^\s*#(.*)$
```
Captures that comment portion.

---

### 377. XML Processing Instruction
```regex
<\?xml\s+[^>]*\?>
```
Matches typical `<?xml version="1.0"?>` lines.

---

### 378. Lines With Two at-signs: e.g. `@user @another`
```regex
^(?:[^@]*@[^@]*@[^@]*)$
```
At least 2 `@` symbols.

---

### 379. Summation Notation: `Σ(...)`
```regex
Σ\(([^)]+)\)
```
Captures text within `Σ(...)`.

---

### 380. Lines That Are Entirely a Single Unicode Emoji (Loose Approx)
```regex
^[\u1F600-\u1F6FF]$
```
Captures some emoticon range, though full emoji range is more complex.

---

### 381. HCL/TF Var Definition: `variable "name" {`
```regex
variable\s+"[^"]+"\s*\{
```
HashiCorp Terraform style.

---

### 382. Detect Sublime/VSCode Snippet Placeholder Like `${1:placeholder}`
```regex
\$\{\d+:[^}]+\}
```
Captures numbered placeholders.

---

### 383. A Basic `.desktop` File Entry
```regex
^[A-Za-z0-9]+=[^\r\n]+
```
Example lines in Linux `.desktop` files.

---

### 384. CSV Fields That Are Quoted but May Contain Escaped Quotes
```regex
"((?:[^"\\]|\\.)*)"
```
Handles `"` pairs inside.

---

### 385. Lines With “```bash” or “```python” (Fenced Code Blocks w/ Language)
```regex
^```(bash|python)\s*$
```
Captures those specific languages.

---

### 386. Simple Comma-Separated Integers with No Spaces
```regex
^\d+(,\d+)*$
```
One or more integers separated by commas.

---

### 387. Unsigned Binary Number (Only 0 or 1)
```regex
^[01]+$
```
No sign, no decimal.

---

### 388. Extract Scenes in a `.cue` File: `TRACK xx AUDIO`
```regex
^TRACK\s+\d+\s+AUDIO\s*$
```
Basic match for track lines.

---

### 389. Lines with “public static void main” (Java)
```regex
^\s*public\s+static\s+void\s+main\s*\(.*\)
```
Identifies the main entry method.

---

### 390. Toml Key with Array: `key = [ ... ]`
```regex
^([A-Za-z0-9_-]+)\s*=\s*\[.*\]$
```
Captures TOML array lines.

---

### 391. Repeated Character Sequences of Exactly 4
```regex
(.)\1{3}
```
E.g. “aaaa”, “####”, etc.

---

### 392. Hex String with Even Length Only
```regex
^(?:[A-Fa-f0-9]{2})+$
```
Pairs of hex digits.

---

### 393. Basic Pascal `program ...;` Declaration
```regex
^\s*program\s+\w+\s*;\s*$
```
Captures a Pascal `program X;` line.

---

### 394. Match Partial IPv4 Mask (e.g., `/24`)
```regex
\/(3[0-2]|[12]\d|[0-9])
```
Ranges 0–32 (CIDR notation).

---

### 395. Docker `FROM` line with optional tag
```regex
^FROM\s+[^\s:]+(?::[^\s]+)?\s*$
```
Captures `FROM ubuntu:latest` or `FROM node`.

---

### 396. A Slack `<#C1234567|channel>` Mention
```regex
<#[A-Z0-9]+(?:\|[^>]+)?>
```
Identifies channel references.

---

### 397. Full HTML Document Declaration
```regex
(?is)^<!DOCTYPE\s+html.*<html.*<\/html>\s*$
```
Multiline match for a minimal HTML structure (approx).

---

### 398. Python Triple Single-Quoted String: `''' ... '''`
```regex
'''([^'\\]|\\.|'(?=[^'])|'{2}(?=[^']))*'''
```
Very approximate, capturing a triple-single-quote block.

---

### 399. INI File Section `[SectionName]` with possible trailing comment
```regex
^\[\s*([^\]]+)\s*\](?:\s*[;#].*)?$
```
Grabs the section name and optional comment.

---

### 400. Currency Symbol Followed by Amount `$123.45`
```regex
^[£€$]\d+(\.\d{1,2})?$
```
Matches typical currency amounts in dollars/euros/pounds.

---

### 401. Lines With Balanced Parentheses and Brackets Simultaneously (Approx PCRE)
```regex
^(?:[^\[\]\(\)]|(\[(?:(?>[^\[\]]+)|(?1))*\])|(\((?:(?>[^\(\)]+)|(?2))*\)))*$
```
Nested structure for parentheses and square brackets. Complex.

---

### 402. Text Surrounded by `<<<` and `>>>`
```regex
<<<([^>]+)>>>
```
Captures inside triple angle brackets.

---

### 403. CamelCase or PascalCase Words
```regex
\b[A-Z][a-z0-9]*([A-Z][a-z0-9]*)*\b
```
Covers sequences of capitalized segments.

---

### 404. Lines That Look Like HTTP Headers (`Name: Value`)
```regex
^[A-Za-z-]+:\s+.*
```
Matches typical HTTP header lines.

---

### 405. Capture Numeric HTML Entities in Dec or Hex
```regex
&#(?:\d+|x[0-9A-Fa-f]+);
```
Handles `&#123;` or `&#x1A;`.

---

### 406. Simple Match for a Metric Unit (e.g., `12 kg`)
```regex
^(\d+(?:\.\d+)?)\s?(cm|mm|kg|g|m|km|l|ml)$
```
Captures unit and numeric value.

---

### 407. Split Key-Value Pairs Separated by “=>”
```regex
([^=]+)=>([^=]+)
```
Often used in Ruby or old Perl styles.

---

### 408. Lines With Possibly Nested `<angle:stuff>` brackets (approx)
```regex
<([^<>]|(?R))*>
```
Recursive pattern in PCRE for `< >`.

---

### 409. Email Subject Lines That Start With `[Bug]`
```regex
^\[Bug\].*
```
Captures lines labeled `[Bug]`.

---

### 410. Git Conflict Markers (`<<<<`, `====`, `>>>>`)
```regex
^(<{7}|={7}|>{7})\s?.*$
```
Find lines showing merge conflict markers.

---

### 411. Python or C++ Style Hex Escapes: `\x00-\xFF`
```regex
\\x[0-9A-Fa-f]{2}
```
Matches hex escape sequences.

---

### 412. Grabs Swift Optional Type `String?`
```regex
\b[A-Z][A-Za-z0-9_]*\?
```
Captures e.g. `String?`.

---

### 413. HTML Hex Char Ref `&#xABCD;`
```regex
&#x[a-fA-F0-9]+;
```
Hex numeric reference.

---

### 414. Lines Containing an Ellipsis `...`
```regex
\.\.\.
```
Simple detection of triple-dot.

---

### 415. Single Tag with `data-` Attribute
```regex
<\w+\b[^>]*\bdata-[a-zA-Z0-9-]+="[^"]*"[^>]*>
```
Finds something like `<div data-value="123">`.

---

### 416. Basic Key-Value Pair in Java Properties (No Comments)
```regex
^([^#!:=\s][^:=\s]*)\s*(=|:)\s*(.*)$
```
Captured group for property key and value.

---

### 417. Find Word Over a Line Break With Hyphen (Word-Wrapping)
```regex
([A-Za-z]+)-\r?\n([A-Za-z]+)
```
Captures splitted words like “wrap-\nping”.

---

### 418. Greek Letters (Unicode Block)
```regex
[\u0370-\u03FF]+
```
Locates Greek characters.

---

### 419. Match a `<meta charset="...">` Tag
```regex
<meta\s+charset\s*=\s*(['"])[^'"]*\1\b[^>]*>
```
HTML5 style.

---

### 420. Check If a Line Is All ASCII
```regex
^[\x00-\x7F]*$
```
No extended chars.

---

### 421. Find `.gitignore`-Style Comments (Lines Starting With `#`)
```regex
^\s*#.*$
```
Captures comments in `.gitignore`.

---

### 422. Capture `.gitmodules` `[submodule "name"]`
```regex
^\[\s*submodule\s+"([^"]+)"\s*\]$
```
Extracts submodule name.

---

### 423. Basic Time Range `09:00-17:00`
```regex
\b([01]\d|2[0-3]):[0-5]\d-([01]\d|2[0-3]):[0-5]\d\b
```
Start-end times in 24-hour format.

---

### 424. Simple For-Loop in JavaScript: `for (...) {`
```regex
^\s*for\s*\([^)]*\)\s*\{\s*$
```
Captures line with basic `for(...) {`.

---

### 425. Match an FQDN or Hostname
```regex
^(?=.{1,253}$)([a-zA-Z0-9-]{1,63}\.)+[a-zA-Z]{2,}$
```
Length-limited domain name check.

---

### 426. Capture `<Link>` in React JSX
```regex
<Link\b[^>]*>([\s\S]*?)<\/Link>
```
Simple find of React `<Link>` component tags.

---

### 427. Lines That Are Only ASCII Punctuation
```regex
^[!-/:-@[-`{-~]+$
```
Excluding letters/digits/whitespace.

---

### 428. Matching a `.scss` Import: `@import "filename";`
```regex
^@import\s+["'][^"']+["'];\s*$
```
Captures SASS/SCSS import lines.

---

### 429. Negative Lookahead for `.png` in URLs
```regex
https?:\/\/(?!.*\.png).+
```
Find URLs not ending in `.png`.

---

### 430. Valid 64-bit Unsigned Integer (0 to 18446744073709551615)
```regex
^(?:0|[1-9]\d{0,19})$
```
No sign, up to 20 digits, but does not strictly compare max.

---

### 431. Labeled Arrows in Text: `--> Label <--`
```regex
-->\s*(\w+)\s*<--
```
Captures a label between arrows.

---

### 432. Haskell-Style Single-Line Comment `--`
```regex
--.*
```
Captures entire line after `--`.

---

### 433. Gherkin Feature Definition: `Feature: ...`
```regex
^Feature:\s+.+$
```
Used in BDD frameworks.

---

### 434. Capture Java Package Declaration: `package com.foo;`
```regex
^\s*package\s+([\w.]+)\s*;\s*$
```
Captures the package path.

---

### 435. Basic XML CDATA Section
```regex
<!\[CDATA\[[\s\S]*?\]\]>
```
Captures everything inside `<![CDATA[...]]>`.

---

### 436. .NET Assembly Info `[assembly: Something("Value")]`
```regex
^\[assembly:\s*\w+\s*\(\s*".*"\s*\)\]$
```
Captures a typical assembly attribute line.

---

### 437. Twitter “Quote Tweet” URL Embedded in text
```regex
https?:\/\/twitter\.com\/[^/]+\/status\/\d+(\?s=\d+)?$
```
Matches a tweet link with optional `?s=` param.

---

### 438. Basic JSON “key”: null
```regex
"([^"]+)"\s*:\s*null
```
Captures a key paired to `null`.

---

### 439. Lines With No Vowels or Digits
```regex
^[^aeiouAEIOU0-9]*$
```
Excludes vowels and numbers entirely.

---

### 440. Markdown-Style Blockquote (`> `) With Two Levels
```regex
^>{2}\s+.*$
```
Captures lines starting with `>>`.

---

### 441. ASCII Control Characters (Non-printable)
```regex
[\x00-\x08\x0B\x0C\x0E-\x1F\x7F]
```
Matches control chars except `\t`, `\n`, `\r`.

---

### 442. A Minimally Valid CSS Selector (just class or id)
```regex
^([.#][A-Za-z_][\w-]*)+$
```
E.g. `.className` or `#id-name`.

---

### 443. Lines Containing Only Balanced Quotation Marks “« »”
```regex
^[^«»]*(«[^«»]*»[^«»]*)*$
```
Pairs of `«...»` only.

---

### 444. YAML Multi-Line String with `|` or `>`
```regex
^[A-Za-z0-9_-]+\s*:\s*[|>][+-]?\s*$
```
Captures the start of a YAML block scalar.

---

### 445. Java Annotation with Parameters `@Annotation(...)`
```regex
@\w+\s*\(\s*[^)]*\)
```
Captures e.g. `@Test(timeout = 1000)`.

---

### 446. Lines With More than 2 Colons (Possible IPv6 expansions)
```regex
^([^:]*:[^:]*){3,}$
```
3 or more `:` pairs.

---

### 447. Basic Bash Function Definition
```regex
^\s*\w+\s*\(\)\s*\{.*$
```
`functionName () { ...`

---

### 448. Capture R Markdown Chunk Header ```{r}
```regex
^```{r([^}]*)}\s*$
```
R code block in an Rmd file.

---

### 449. Advanced Postgres `COPY` Statement
```regex
^COPY\s+\w+(\.\w+)?\s+FROM\s+('|")[^'"]+\2\s*.*;$
```
Captures table with optional schema, file path, etc.

---

### 450. Strings with a Possibly Escaped Backslash at the End
```regex
\\?$
```
End of line with zero or one backslash.

---

### 451. Substitution Placeholder Like `$1` or `$2`
```regex
\$\d+
```
For replacement references in many regex engines.

---

### 452. Golang Import Statement with Alias: `import alias "package"`
```regex
^\s*import\s+\w+\s+"[^"]+"\s*$
```
Captures lines specifying an import alias.

---

### 453. Lines That End With a Period, Exclamation, or Question
```regex
[.!?]\s*$
```
Sentence terminator at line end.

---

### 454. MySQL `INSERT INTO table (...) VALUES (...);`
```regex
^INSERT\s+INTO\s+\w+\s*\([^)]*\)\s+VALUES\s*\([^)]*\);\s*$
```
Basic pattern for a single-line INSERT statement.

---

### 455. Python Class Definition With Inheritance
```regex
^\s*class\s+[A-Za-z_]\w*\(\s*[A-Za-z_]\w*\s*\)\s*:\s*$
```
Class extends another class.

---

### 456. C++ Class Template Declaration
```regex
^\s*template\s*<[^>]+>\s*class\s+\w+
```
Captures `template<typename T> class MyClass`.

---

### 457. Windows-Style IP + Port in `XXX.XXX.XXX.XXX:PORT`
```regex
^\d{1,3}(\.\d{1,3}){3}:\d+$
```
Find lines with IP:Port.

---

### 458. Strings Containing “foo” or “bar”, but Not Both
```regex
^(?:(?!.*bar).*foo.*|(?:(?!.*foo).*bar.*))$
```
Either “foo” or “bar” exclusively, not both.

---

### 459. Elm Module Declaration: `module Name exposing (..)`
```regex
^module\s+[A-Z][A-Za-z0-9]*(?:\.[A-Z][A-Za-z0-9]*)*\s+exposing\s*\((?:[^)]*)\)\s*$
```
Captures Elm module lines.

---

### 460. ASCII Letters or Emojis Only (Very Rough)
```regex
^[A-Za-z\u1F600-\u1F6FF]+$
```
Allow letters and a small block of emojis.

---

### 461. CSV Row With Exactly 5 Fields
```regex
^(?:[^,]*,){4}[^,]*$
```
Four commas = five fields.

---

### 462. 24-Hour Time Spanning Midnight (e.g., `23:00-02:00`)
```regex
^([01]\d|2[0-3]):[0-5]\d-([01]\d|2[0-3]):[0-5]\d$
```
Basic times separated by dash.

---

### 463. `.po` File msgid or msgstr lines
```regex
^(msgid|msgstr)\s+"(?:[^"\\]|\\.)*"\s*$
```
Captures translation lines.

---

### 464. C++ Preprocessor Include
```regex
^\s*#\s*include\s*(<[^>]+>|"[^"]+")\s*$
```
Captures both `<header>` and `"header"` forms.

---

### 465. IPv4 with Leading Zeroes (Detect them specifically)
```regex
\b0\d+\.\d+\.\d+\.\d+|\.\b0\d+\b
```
At least one octet starts with zero. (Might be partial. Adjust as needed.)

---

### 466. JSDoc-Like Comment `/**  ... */`
```regex
\/\*\*[\s\S]*?\*\/
```
Captures `/** ... */`. Different from standard `/*`, but for JSDoc.

---

### 467. Match 3 or More `#` in a Row
```regex
#{3,}
```
At least triple `#`.

---

### 468. ReStructuredText Link Definition
```regex
^..\s+_.*?:\s+https?://\S+$
```
Captures something like `.. _my-link: https://site`.

---

### 469. HTML Tag With `on`-Event Attribute (e.g., `onclick=`)
```regex
<\w+\b[^>]*\son[a-z]+\s*=\s*(['"])[^'"]*\1[^>]*>
```
Finds tags with inline event handlers.

---

### 470. Lines with `@param` in JavaDoc
```regex
^\s*\*\s*@param\s+\w+
```
Captures parameter doc lines.

---

### 471. Python-Type Hinted Function Param: `def func(arg: type):`
```regex
def\s+\w+\s*\([^)]*\:\s*[\w\[\],]+\)\s*:
```
Roughly finds function with typed parameter.

---

### 472. Hex Color With Alpha Channel `#RRGGBBAA`
```regex
#[0-9A-Fa-f]{8}
```
8 hex digits.

---

### 473. `<a target="_blank" ...>` Link
```regex
<a\b[^>]*\btarget="_blank"\b[^>]*>
```
Captures anchor tags with `target="_blank"`.

---

### 474. Capture Negative Exponential Number `-1.23e-4`
```regex
^-?\d+(\.\d+)?[eE]-?\d+$
```
Signed exponent is allowed.

---

### 475. Lines That Are Bare Git Submodule URLs
```regex
^(?:git@|https?:\/\/)\S+\/\S+(\.git)?$
```
e.g., `git@github.com:User/Repo.git`.

---

### 476. CMake Command `add_executable(...)`
```regex
^\s*add_executable\s*\([^)]*\)
```
Captures `add_executable(...)` lines.

---

### 477. Lines With No Lowercase Letters
```regex
^[^a-z]*$
```
Excludes `a-z`.

---

### 478. Ruby Symbol Regex `:\w+` (but not `:"string"` form)
```regex
(?<!"):\b[A-Za-z_]\w*
```
Finds plain colon symbols, ignoring quoted forms.

---

### 479. Org-Mode Heading Lines Start With `* `  
```regex
^\*+\s+.*$
```
Captures single or multiple stars at line start.

---

### 480. Find “\uXXXX” Unicode Escapes in JSON
```regex
\\u[0-9A-Fa-f]{4}
```
Hex-coded Unicode in JSON.

---

### 481. Basic CLI Option Pattern: `--option=value`
```regex
^--[A-Za-z0-9_-]+=.+$
```
Captures `--key=value`.

---

### 482. Validate a 3-Byte RGB Hex Code (No Leading `#`)
```regex
^[A-Fa-f0-9]{6}$
```
6 hex digits, without `#`.

---

### 483. Lines With Balanced Pairs of Curly Braces and Square Brackets (Approx)
```regex
^(?!.*(\{[^{}]*\[|\[[^\[\]]*\{)[\s\S]*?(\}|\]))[\s\S]*$
```
A negative lookahead approach to ensure no mismatched nesting. Very approximate.

---

### 484. Lines That Contain Only a Single Punctuation Mark
```regex
^[^!-/:-@[-`{-~]*[!-/:-@[-`{-~][^!-/:-@[-`{-~]*$
```
Exactly one punctuation char.

---

### 485. GFM Task List Item: `- [ ]` or `- [x]`
```regex
^- \[( |x)\]\s+.*$
```
Markdown tasks.

---

### 486. Extract Domain from an Email, ignoring subdomain
```regex
@(?:[^.]+\.)*([^.]+\.[^.]+)$
```
Group 1 is the last two parts.

---

### 487. Lines That Start With `0x` But Are Not `0x0`
```regex
^0x(?!0$)[A-Fa-f0-9]+$
```
Hex lines not equal to `0x0`.

---

### 488. Capture Balanced “( … )” With Allowed Nested Parentheses (PCRE)
```regex
\((?:[^()]+|(?R))*\)
```
Recursive subpattern for nesting.

---

### 489. Markdown reference link `[id]: URL "title"`
```regex
^\[([^\]]+)\]:\s+(\S+)(?:\s+"[^"]*")?$
```
Captures reference definitions.

---

### 490. ASCII Letters in Title Case (e.g., “Hello World”)
```regex
^([A-Z][a-z]+)(\s+[A-Z][a-z]+)*$
```
Multiple words, each TitleCased.

---

### 491. Allowed Username: Start letter, then letters/digits, 3-20 total
```regex
^[A-Za-z][A-Za-z0-9]{2,19}$
```
Minimum length 3, max 20.

---

### 492. Lines That Contain `TODO:` Or `FIXME:` But Not Both
```regex
^(?:(?!.*FIXME:).*TODO:.*|(?:(?!.*TODO:).*FIXME:.*))$
```
Either “TODO” or “FIXME,” exclusively.

---

### 493. Basic TypeScript Interface Declaration
```regex
^\s*interface\s+\w+\s*\{\s*$
```
Captures `interface Name {`.

---

### 494. `sed`-style Substitution Command `s/pattern/replacement/g`
```regex
^s\/([^/]+)\/([^/]*)\/([gp]|([gpx]|([gpx]|\d+))*)?$
```
Somewhat flexible. Adjust as needed.

---

### 495. Identifying a MAC Address with Dots: `XXXX.XXXX.XXXX`
```regex
^[A-Fa-f0-9]{4}\.[A-Fa-f0-9]{4}\.[A-Fa-f0-9]{4}$
```
Cisco style.

---

### 496. Java “throws” Clause
```regex
throws\s+[A-Z][A-Za-z0-9]*(?:Exception|Error)\b
```
Roughly find an exception thrown.

---

### 497. C# `namespace X.Y` Declaration
```regex
^\s*namespace\s+[\w\.]+\s*$
```
Captures namespace lines.

---

### 498. String With Both Letters and Hyphens Only
```regex
^[A-Za-z-]+$
```
No digits or other punctuation.

---

### 499. Matches a Single Surrogate High Followed by Surrogate Low
```regex
[\uD800-\uDBFF][\uDC00-\uDFFF]
```
UTF-16 surrogate pair.

---

### 500. Lines That Contain a Unicode Zero-Width Space (U+200B)
```regex
\u200B
```
Detect “zero-width space” in text.

---

### 501. Match Lines Containing Both Uppercase and Non-Alphanumeric Characters
```regex
^(?=.*[A-Z])(?=.*[^A-Za-z0-9]).*$
```
Ensures a line has at least one uppercase letter and at least one symbol/punctuation character.

---

### 502. Find Strings Surrounded by @ @ (Literal At Symbols)
```regex
@([^@]+)@
```
Captures text between `@...@`.

---

### 503. Match a Single-Quoted String in Shell Script That Continues (Multiline)
```regex
'([^'\\]*(\\.[^'\\]*)*)'
```
Allows escaped characters within single quotes across multiple lines.

---

### 504. Simple Markdown Italic `*text*` (No Nesting)
```regex
\*([^*]+)\*
```
Finds italic text wrapped in asterisks, ignoring nested cases.

---

### 505. Basic .NET Generic Type Declaration (e.g., `List<int>`)
```regex
^[A-Z][A-Za-z0-9_]*(?:<[A-Za-z0-9_]+>)?$
```
Captures a type name with optional single-type generic parameter.

---

### 506. Consecutive Repeated Pairs (e.g., `ababab`)
```regex
^(\w\w)+$
```
Any two-character pattern repeated one or more times.

---

### 507. Find HTML Comments That Contain “TODO”
```regex
<!--[^>]*TODO[^>]*-->
```
Looks inside `<!-- ... -->` for the word “TODO.”

---

### 508. Match a File with `.md` or `.markdown` Extension
```regex
^[^\\/:*?"<>|]+\.(?:md|markdown)$
```
Validates a Markdown filename, ignoring path separators.

---

### 509. Jinja-Style Template Blocks: `{% ... %}`
```regex
\{\%[^%]*\%\}
```
Captures Jinja (or Twig) control statements like `{% if ... %}`.

---

### 510. Lines Containing a `$` but Not a Shell Variable Reference
```regex
^(?=.*\$)(?!.*\$\{?[A-Za-z_]\w*).*$
```
Ensures `$` exists but not in a typical variable format like `$VAR` or `${VAR}`.

---

### 511. Words Longer Than 10 Characters
```regex
\b\w{11,}\b
```
Captures any “word” with 11+ characters.

---

### 512. Validate a Unix Timestamp (Seconds Since Epoch) Up to 2147483647
```regex
^(?:0|[1-9]\d{0,9}|1\d{9}|20\d{8}|21[0-3]\d{7}|214[0-6]\d{6}|2147[0-2]\d{5}|21474[0-7]\d{4}|214748[0-2]\d{3}|2147483[0-5]\d{2}|21474836[0-3]\d|214748364[0-7])$
```
Checks numeric range [0..2147483647].

---

### 513. CamelCase Without Numbers (Strict Letters Only)
```regex
^[A-Z][a-z]+(?:[A-Z][a-z]+)*$
```
Example: `CamelCaseWord`.

---

### 514. Match a Python Boolean in Code: `True` or `False` (Whole Word)
```regex
\b(?:True|False)\b
```
Distinguishes these keywords in Python code.

---

### 515. Finds Text with Consecutive “xyz” Repeated 2+ Times
```regex
(xyz)\1+
```
Captures sequences like `xyzxyz`, `xyzxyzxyz`.

---

### 516. ISO8601-Like DateTime (No Timezone) `YYYY-MM-DDTHH:MM:SS`
```regex
^\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}$
```
Minimal strict pattern, e.g. `2025-12-31T23:59:59`.

---

### 517. Capture `sudo` Commands (Rudimentary)
```regex
^\s*sudo\s+.+$
```
Find lines starting with “sudo.”

---

### 518. Java Lambda With Parameters: `(Type1 x, Type2 y) ->`
```regex
\(\s*[A-Za-z_]\w*\s+[A-Za-z_]\w*(?:\s*,\s*[A-Za-z_]\w*\s+[A-Za-z_]\w*)*\)\s*-> 
```
Captures a typed parameter list arrow in Java.

---

### 519. Keyframe Definitions in CSS: `@keyframes name { ... }`
```regex
@keyframes\s+[A-Za-z0-9_-]+\s*\{[\s\S]*?\}
```
Matches an entire `@keyframes` block.

---

### 520. Windows-Style UNC Path (e.g., `\\Server\Share`)
```regex
^\\\\[A-Za-z0-9._-]+\\[^\\]+
```
Captures basic UNC network paths.

---

### 521. Checks If a String Contains Only Zero or One Space
```regex
^[^\s]*\s?[^\s]*$
```
Either no space or exactly one space.

---

### 522. Golang Struct Declaration
```regex
type\s+[A-Z]\w*\s+struct\s*\{\s*[^}]*\}
```
Captures lines like `type MyStruct struct { ... }`.

---

### 523. Perl `use strict;` or `use warnings;` Statement
```regex
^\s*use\s+(strict|warnings);\s*$
```
Finds typical Perl pragmas.

---

### 524. Disallows 4 Consecutive Identical Characters
```regex
^(?!.*(.)\1{3}).*$
```
Negative lookahead for a quadruple repeat.

---

### 525. Simple Dockerfile `CMD ["executable"]` With Single Arg
```regex
^CMD\s+\[\s*"[^"]+"\s*\]$
```
One-argument `CMD`.

---

### 526. Find a Shortcut Syntax for Python Type Hints: `-> ReturnType:`
```regex
->\s*[A-Za-z_][\w\[\],\s]*(?=:)
```
Captures return type annotation in Python.

---

### 527. Identify Webpack `require()` Calls
```regex
require\s*\(\s*['"][^'"]+['"]\s*\)
```
Captures JS `require('module')`.

---

### 528. Extract a `.NET` Assembly Version `[assembly: AssemblyVersion("1.2.3.4")]`
```regex
\[assembly:\s*AssemblyVersion\s*\(\s*"([^"]+)"\s*\)\]
```
Group 1 captures the version.

---

### 529. Lines Containing Balanced “<>” but Not HTML Tags (Trick)
```regex
^((?!<\w+>).*<[^>]*>[^<]*)+$
```
Approx approach to ensure “<...>” without typical tag patterns. Might be engine-specific.

---

### 530. Check for Balanced Double Quotes in a Single Line (Even Number)
```regex
^([^"]*"[^"]*")*[^"]*$
```
Basic approach: pairs of quotes repeated.

---

### 531. Matches JSON “key”: “string with \”escape\””
```regex
"([^"]+)"\s*:\s*"([^"\\]|\\.)*"
```
Captures a key-value with string escaping inside the value.

---

### 532. Entire String Is a Quoted Word with Optional Leading/Trailing Spaces
```regex
^\s*"[^"]+"\s*$
```
Line with optional whitespace around one quoted word.

---

### 533. Lines With Unicode Block for Cyrillic
```regex
[\u0400-\u04FF]+
```
Find sequences of Cyrillic chars.

---

### 534. Single Hex Digit Followed by a Colon Then 2 Decimal Digits
```regex
^[A-Fa-f0-9]:\d{2}$
```
Pattern like `F:23`.

---

### 535. Simple Docker Image Tag (No Slash)
```regex
^[a-zA-Z0-9._-]+:[A-Za-z0-9._-]+$
```
Matches `image:tag` with no repo path.

---

### 536. Detect `<iframe>` Tags With `srcdoc` Attribute
```regex
<iframe\b[^>]*\bsrcdoc\s*=\s*(['"])[\s\S]*?\1[^>]*>
```
Find iframe tags using `srcdoc`.

---

### 537. Minimal MP3 File Extension
```regex
^.+\.mp3$
```
Captures `.mp3` at line end.

---

### 538. JSON “key”: number (with fraction or exponent)
```regex
"([^"]+)"\s*:\s*-?\d+(?:\.\d+)?(?:[eE][+\-]?\d+)?
```
Handles numeric values in JSON.

---

### 539. Vim Modeline: `vim: set ... :`
```regex
vim?:\s*set\s+[^:]+:
```
Captures typical `# vim: set ts=4 :` lines.

---

### 540. Identify Docker `ENV` with multiple variables
```regex
^ENV\s+([\w_]+\s*=\s*[^=]+)(\s+[\w_]+\s*=\s*[^=]+)+$
```
Multiple assignments in one `ENV` line.

---

### 541. Check for Balanced Angle Brackets in a Single Tag (No Nesting)
```regex
^<[^<>]*>$
```
One set of `<>` only, no nested tags.

---

### 542. Alphanumeric ASCII but Must End with a Letter
```regex
^[A-Za-z0-9]*[A-Za-z]$
```
Enforces final character is a letter.

---

### 543. Extract Attribute Names in an HTML Tag
```regex
([a-zA-Z_:][-a-zA-Z0-9_:.]*)(?=\s*=\s*(['"]?)[^'">]*\2)
```
Captures the attribute name portion before `=`.

---

### 544. Simplistic Rust `struct` Declaration
```regex
^\s*struct\s+[A-Z][A-Za-z0-9_]*\s*\{\s*[^}]*\}\s*$
```
Captures lines like `struct MyType { ... }`.

---

### 545. Lines With an Odd Number of Digits
```regex
^(?:[^0-9]*[0-9][^0-9]*[0-9])*[^0-9]*[0-9][^0-9]*$
```
Requires counting. This pattern pairs digits, then ensures one leftover digit.

---

### 546. CSS Class Names with BEM Format
```regex
^[a-z0-9]+(?:-[a-z0-9]+)*(?:__[a-z0-9]+(?:-[a-z0-9]+)*)?(?:--[a-z0-9]+(?:-[a-z0-9]+)*)?$
```
Basic [Block__Element--Modifier](https://en.bem.info/methodology/) naming style.

---

### 547. HTML Tag with a Data-Attribute Key That Contains a Colon
```regex
<\w+\b[^>]*\bdata-[^=\s]*:[^=\s]*=[^>]*>
```
Finds attributes like `data-foo:bar="value"`.

---

### 548. Match a Word That Contains `q` but Not `u` After It
```regex
\b\w*q(?!u)\w*\b
```
English-based check for “q” not followed by “u.”

---

### 549. ID3v1 Tag in a Binary File (At End): `TAG` at Byte 128 from End
```regex
TAG(.{30}).{30}.{30}.{4}.{30}.{1}.{1}
```
Approx. Actual usage depends on editor’s binary find capabilities.

---

### 550. Lines With an Even Number of Quoted Strings
```regex
^(?:(?:[^"]*"[^"]*"){2})*[^"]*$
```
Every 2 quotes is a single string, ensure even pairs.

---

### 551. MAC Address in EUI-64 Format `xx:xx:xx:xx:xx:xx:xx:xx`
```regex
\b[0-9A-Fa-f]{2}(:[0-9A-Fa-f]{2}){7}\b
```
Longer EUI-64.

---

### 552. Simple IPv6 + Optional Port `[::1]:8080`
```regex
^\[([0-9A-Fa-f:]+)\](?::(\d{1,5}))?$
```
Find `[ipv6]:port`.

---

### 553. Python-Style Named Parameters in Function Calls: `func(param=value)`
```regex
\w+\(\s*\w+\s*=\s*[^()]+(?:\s*,\s*\w+\s*=\s*[^()]+)*\)
```
Captures calls with named args.

---

### 554. Minimal Valid Email “mailto:” Link
```regex
mailto:[a-zA-Z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}
```
Mailto links.

---

### 555. Time in `HH:MM` Format With Leading Zero if Single-Digit Hour
```regex
^(0\d|1\d|2[0-3]):[0-5]\d$
```
24-hour clock up to `23:59`.

---

### 556. Vowel-Only Words (At Least One Character)
```regex
^[aeiouAEIOU]+$
```
Captures lines with only vowels.

---

### 557. Java `System.out.println("...");`
```regex
System\.out\.println\s*\(\s*"[^"]*"\s*\)\s*;
```
Matches straightforward usage.

---

### 558. Leading and Trailing Punctuation, But Not in the Middle
```regex
^[!-/:-@[-`{-~]*[^!-/:-@[-`{-~].*[^!-/:-@[-`{-~][!-/:-@[-`{-~]*$
```
Any punctuation allowed at extremes only.

---

### 559. Numeric Values Larger Than 9999 (Digit Based)
```regex
^[1-9]\d{4,}$
```
5 or more digits, ignoring sign.

---

### 560. Lines With Only `A` and `B` (No Other Letters)
```regex
^[AB]+$
```
Restricts line to `A`/`B`.

---

### 561. .NET Format Strings Like `"{0}"`, `"{1:C}"`, ignoring internal braces
```regex
"\{\d+[^}]*\}"
```
Find placeholders like `"{0}"`.

---

### 562. Python Format Specifiers in f-strings: `{var:.2f}`
```regex
\{[A-Za-z_]\w*:\.[0-9]+[a-zA-Z]\}
```
Example: `{price:.2f}`.

---

### 563. `<script type="module"> ... </script>` Tags
```regex
<script\b[^>]*\btype\s*=\s*(["'])module\1[^>]*>([\s\S]*?)<\/script>
```
Captures ES module script blocks.

---

### 564. Semi-Strict Numeric Month Range (01–12)
```regex
^(0[1-9]|1[0-2])$
```
Valid months in two-digit format.

---

### 565. BFS-Style Alphanumeric Check with Single Underscore Allowed
```regex
^[A-Za-z0-9]+(?:_[A-Za-z0-9]+)?$
```
Zero or one underscore in the string.

---

### 566. Lines with `public:` in C++ Class
```regex
^\s*public:\s*$
```
Matches standard access specifier line.

---

### 567. XSD Decimal Type: Digits with Optional Fraction
```regex
^-?\d+(\.\d+)?$
```
Basic decimal with optional sign.

---

### 568. Empty `<div>` (No Content)
```regex
<div\b[^>]*>\s*<\/div>
```
Captures a `div` with nothing inside.

---

### 569. Punycode Domain: `xn--...`
```regex
xn--[a-z0-9]+
```
IDN punycode prefix.

---

### 570. Lines That Start With a Greek Character
```regex
^[\u0370-\u03FF].*$
```
First character in Greek range.

---

### 571. Swift `if let` Binding
```regex
^\s*if\s+let\s+[A-Za-z_]\w*\s*=\s*[^=]+$
```
Captures lines like `if let name = dictionary["name"]`.

---

### 572. Captures Markdown Link Text Without URL: `[text](()`
```regex
\[([^\]]+)\]\(\)
```
Find `[foo]()` missing link target.

---

### 573. ASCII Only, No Digits
```regex
^[\x00-\x7F&&[^0-9]]+$ 
```
Non-digit ASCII characters only. Some engines might differ in bracket usage.

---

### 574. “Binary” Data – Only 0/1 and Optional Leading 0b
```regex
^(?:0b)?[01]+$
```
Matches e.g. `0b1010` or `1010`.

---

### 575. Lines Ending with a Curly Arrow `}-->`
```regex
\}-->$
```
Find lines that conclude with `}-->`.

---

### 576. Multiple Decimal or Hex Integers in a Row (e.g., “123 0x1A 456”)
```regex
(?:\b\d+\b|\b0x[A-Fa-f0-9]+\b)(?:\s+(?:\b\d+\b|\b0x[A-Fa-f0-9]+\b))*
```
Space-separated decimal or hex values.

---

### 577. Ruby `elsif`
```regex
^\s*elsif\s+.*$
```
Matches lines that start an `elsif` condition.

---

### 578. Lines Containing `chown user:group` with or without “sudo”
```regex
^(?:sudo\s+)?chown\s+\S+:\S+
```
Finds a `chown` usage, optionally with `sudo`.

---

### 579. HTML `colspan` or `rowspan` Attributes in Table Cells
```regex
<(td|th)\b[^>]*\b(colspan|rowspan)\s*=\s*(['"])\d+\3[^>]*>
```
Captures cell tags with either `colspan` or `rowspan`.

---

### 580. Java `String[] args` in Method Declaration
```regex
String\[\]\s+args
```
Typical main param in Java.

---

### 581. Single Underscore Surrounded by Letters: `a_b`
```regex
\B_[a-zA-Z]+\B
```
No word boundary around `_`.

---

### 582. URI Fragment Only: `#section`
```regex
^#[^#?]+$
```
Captures a fragment alone.

---

### 583. Bash-Style Arithmetic Expansion: `$(( ... ))`
```regex
\$\(\([^)]*\)\)
```
Find `$(( expression ))`.

---

### 584. Haskell Module Declaration: `module Name where`
```regex
^module\s+[A-Z][A-Za-z0-9.]*\s+where\s*$
```
Captures line stating a module name.

---

### 585. Negative or Positive Infinity in Float Format
```regex
^-?Infinity$
```
Checks for `Infinity` or `-Infinity`.

---

### 586. Basic NuGet Package Reference `<PackageReference Include="...">`
```regex
<PackageReference\s+Include\s*=\s*(['"])[^'"]+\1[^>]*>
```
MSBuild-style references.

---

### 587. Five or More Consecutive Word Characters
```regex
\w{5,}
```
Locates runs of 5+ word chars.

---

### 588. Gnuplot Comment Lines Starting With `#`
```regex
^\s*#.*$
```
Simple detection of comment lines.

---

### 589. Lines That Contain a Single “@” and No Other Symbol
```regex
^[^@]*@[^@]*$
```
Exactly one `@` in the entire line.

---

### 590. `<audio>` Tag With `controls` Attribute
```regex
<audio\b[^>]*\bcontrols\b[^>]*>
```
Find HTML5 audio tags with controls.

---

### 591. Email Addresses That Use a “+tag” Format
```regex
[a-zA-Z0-9._%+-]+(\+[a-zA-Z0-9._%+-]+)?@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}
```
Allows `user+tag@example.com`.

---

### 592. Lines That Do Not Start With a Word Character
```regex
^[^\w].*$
```
Ensures the first character is non-word.

---

### 593. “Sticky” Unclosed Quote at the End (like `'some text`)
```regex
'(?:[^']*)$
```
Find a single quote without closing.

---

### 594. Capture Remote Branch in Git Output: `origin/feature_x`
```regex
^[A-Za-z0-9._-]+\/[A-Za-z0-9._-]+$
```
Matches a typical `remote/branch`.

---

### 595. Shell Variable Assignments `NAME=VALUE` (No Spaces)
```regex
^[A-Za-z_]\w*=[^\s]+$
```
Shell style var=val line.

---

### 596. Simple .ini Key with Dot Notation: `key.subkey=value`
```regex
^([\w-]+\.)+[\w-]+\s*=\s*.*$
```
Example: `app.database.user=admin`.

---

### 597. Pairs of Letters Separated by a Single Hyphen: `A-B C-D`
```regex
(?:[A-Za-z]-[A-Za-z])(?:\s+[A-Za-z]-[A-Za-z])*
```
Multiple pairs spaced out.

---

### 598. Lines With “print” But Not “printf”
```regex
^(?=.*\bprint\b)(?!.*\bprintf\b).*$
```
Look for “print” while excluding “printf.”

---

### 599. Strict UPPER_SNAKE_CASE (No Digits)
```regex
^[A-Z]+(?:_[A-Z]+)*$
```
All uppercase letters, underscores only.

---

### 600. Capture ASCII Letters That Appear in Pairs (AA, BB, CC)
```regex
([A-Za-z])\1
```
Find repeated letter pairs.

---

### 601. Lines Ending With a Slash and a Digit
```regex
\/\d$
```
Slash immediately followed by one digit at line end.

---

### 602. Check for a Minimal JS Arrow Function Without Parentheses: `param => expr`
```regex
^[A-Za-z_$]\w*\s*=>\s*[^{};]+$
```
No braces or multiple parameters.

---

### 603. Grabs an Interpolated Bash Variable in a String: `"some $VAR text"`
```regex
"\$[A-Za-z_]\w*"
```
Inside double quotes, a `$VAR`.

---

### 604. `<button>` Tag Without a `type` Attribute
```regex
<button\b((?!\btype\b)[^>])*> 
```
Find button tags missing `type`.

---

### 605. Lines With `while` but Not `endwhile`
```regex
^(?=.*\bwhile\b)(?!.*\bendwhile\b).*$
```
Used in some templating languages or old shells.

---

### 606. UTF-8 Byte Order Mark (BOM) at Start of File
```regex
^\xEF\xBB\xBF
```
Hex-coded BOM bytes.

---

### 607. Plaintext IPv4 CIDR: `192.168.0.0/16`
```regex
\b(?:\d{1,3}\.){3}\d{1,3}\/(?:[0-2]\d|3[0-2]|[0-9])\b
```
Matches 0–32 bit prefix.

---

### 608. Python’s `elif` with Colon
```regex
^\s*elif\s+.*:\s*$
```
Captures a typical `elif something:` line.

---

### 609. HTML Tag With Closing “/>” But Missing Space: `<img/>`
```regex
<\w+[^>]*\/>
```
Self-closing tag with no space. Some HTML validators warn about it.

---

### 610. JS Decorators (Experimental Syntax): `@decorator`
```regex
^@\w[\w.]*
```
Captures lines starting with an @decorator.

---

### 611. Full-Width ASCII Letters [FF01-FF5E] (Half/Full-Width forms)
```regex
[\uFF01-\uFF5E]+
```
Matches halfwidth/fullwidth ASCII range.

---

### 612. YAML “- key: value” Structure
```regex
^-\s+[A-Za-z0-9_-]+\s*:\s*.+$
```
A list item with a key-value in YAML.

---

### 613. Java `System.err.println(...)`
```regex
System\.err\.println\s*\([^)]*\)\s*;
```
Similar to `System.out.println`, but with `err`.

---

### 614. No Leading or Trailing Slash, But Slashes Allowed Inside
```regex
^[^/].*[^/]$
```
String does not begin or end with `/`.

---

### 615. Expand Tabs to 4 Spaces (Find Tabs)
```regex
\t
```
Use replacement of four spaces in many editors.

---

### 616. Gaps of 2+ Consecutive Digits Separated by a Non-Digit
```regex
\d{2,}\D+\d{2,}
```
Two or more digits, then separator, then two or more digits.

---

### 617. One or More HTML Entities in a Row
```regex
(&[a-zA-Z0-9]+;)+
```
E.g. `&amp;&gt;`.

---

### 618. Simple Nginx Config Comment `# ...`
```regex
^\s*#.*$
```
Removes comment lines.

---

### 619. Merge Markers: `^=+$` (like in patch diffs)
```regex
^=+$
```
A line of equals.

---

### 620. Lines That Start With `-` or `+` But Not `--` or `++`
```regex
^(?![-+]{2})[-+].*$
```
Single minus/plus at start only.

---

### 621. Loose US/CA Province/State Name (One Word)
```regex
^(Alabama|Alaska|Arizona|...|Yukon)$
```
Would be huge for all states/provinces. Example pattern structure.

---

### 622. Debian Control File Field: `Key: value`
```regex
^[A-Za-z0-9-]+:\s+.*$
```
Captures lines like `Package: mypackage`.

---

### 623. One or More Digits Followed by “GB” or “MB”
```regex
^\d+(?:GB|MB)$
```
Simple data size like `16GB`.

---

### 624. Linux Syslog Timestamp: `MMM dd HH:MM:SS`
```regex
^[A-Z][a-z]{2}\s+\d{1,2}\s+\d{2}:\d{2}:\d{2}
```
Captures e.g. `Mar 12 10:01:23`.

---

### 625. Plain Text Control Character (Bell, \x07)
```regex
\x07
```
Bell char in text.

---

### 626. HTML Opening Tag Name Only
```regex
^<([A-Za-z][A-Za-z0-9-]*)(?=\s|>|\/>)
```
Captures the tag name from an opening tag.

---

### 627. Shell Shebang Specifically for `/bin/sh`
```regex
^#!\s*/bin/sh\s*$
```
Exact line check.

---

### 628. JSON Five-Digit String Key: `"12345": ...`
```regex
^"\d{5}":\s*
```
Within JSON structure, a numeric key of length 5.

---

### 629. Strings That End in a Two-Digit Year `’23`
```regex
’\d{2}$
```
Using a right single quote then two digits, e.g. `’23`.

---

### 630. Unicode Punctuation Category (General)
```regex
\p{P}+
```
Matches any punctuation character from Unicode classes.

---

### 631. Swift Generic Function Declaration `func name<T> ...`
```regex
^\s*func\s+[A-Za-z_]\w*\s*<[^>]+>\s*\(.*\)
```
Captures generics in Swift.

---

### 632. Balanced Single-Quotes with Possible Escapes Inside
```regex
'((\\')|[^'])*'
```
Allows for escaped single quotes.

---

### 633. Markdown List with Numbers: `1. item`
```regex
^\d+\.\s+.*$
```
Simple numeric list pattern.

---

### 634. Lines Containing Balanced Pair of `%% ... %%`
```regex
%%[^%]*%%
```
Captures text enclosed by double-percent markers.

---

### 635. CamelCase Words With No Lowercase
```regex
^[A-Z]+([A-Z]+)*$
```
All uppercase letters in blocks. Example: `XMLHTTPRequest`.

---

### 636. Extract `sqlite://` or `postgresql://` URIs
```regex
^(sqlite|postgresql):\/\/[\S]+$
```
Starts with `sqlite://` or `postgresql://`.

---

### 637. Any Word Followed by a `:` Then Another Word: `foo:bar`
```regex
\b\w+:\w+\b
```
Simple `key:value` tokens.

---

### 638. Hex-coded ASCII Escapes \xHH repeated
```regex
(\\x[A-Fa-f0-9]{2})+
```
One or more sequences of `\xNN`.

---

### 639. HTML Tag Pair Where the Closing Tag Has Extra Slash
```regex
<(\w+)[^>]*>[\s\S]*?<\s*/\1\s*/>
```
Identifies `<tag>...</tag/>`, an invalid closing.

---

### 640. `$PS1` Variable in a Shell Script
```regex
^\s*PS1\s*=\s*(['"]).*\1
```
Captures line assigning `$PS1` with quotes.

---

### 641. Non-Greedy `.*?` Until a Comma
```regex
^([^,]*),
```
Captures everything until the first comma.

---

### 642. HTML `<meta name="description" content="...">`
```regex
<meta\s+name\s*=\s*(['"])description\1\s+content\s*=\s*(['"])(.*?)\2[^>]*>
```
Grabs description meta content.

---

### 643. Captures a Balanced Pair of Braces That May Include Commas
```regex
\{[^{}]*?(,[^{}]*?)*\}
```
Approx. No nesting accounted.

---

### 644. SRT Subtitle Time Range `HH:MM:SS,mmm --> HH:MM:SS,mmm`
```regex
\d{2}:\d{2}:\d{2},\d{3}\s-->\s\d{2}:\d{2}:\d{2},\d{3}
```
Typical subtitle time format.

---

### 645. Lines That Start With `if(` in C/Java (No Space)
```regex
^if\(
```
Captures `if(condition)` with no space.

---

### 646. YAML Tag Declaration: `!someTag`
```regex
^!\w+
```
At start of line.

---

### 647. A Basic JSON Array of Integers Only
```regex
\[\s*\d+(?:\s*,\s*\d+)*\s*\]
```
Captures `[1, 2, 3]`.

---

### 648. MS DOS-Style Label: `[LABEL]` in Uppercase
```regex
^\[[A-Z0-9_]+\]$
```
Captures bracketed uppercase alphanumerics.

---

### 649. Rust Lifetime Annotation `<'a>` in a Function Signature
```regex
fn\s+\w+\s*<['a-zA-Z_,\s]+>\s*\([^)]*\)
```
Rough capture of lifetimes.

---

### 650. Keyboard Shortcut Notation: `Ctrl+Alt+X`
```regex
^[A-Z][a-zA-Z]*\+(?:[A-Z][a-zA-Z]*\+)*[A-Za-z0-9]$
```
Chain of keys joined by `+`.

---

### 651. Kotlin `when` Statement Start
```regex
^\s*when\s*\(\s*\w+\s*\)\s*\{\s*$
```
Matches a Kotlin `when` block.

---

### 652. Lines That Contain a Capital “I” Followed by Zero or More “l” (Lower L)
```regex
I[l]* 
```
Example: `Il`, `Illl`.

---

### 653. Detect a Double Slash in a URL Path (Not Protocol)
```regex
^(?!https?:\/\/)(.*\/\/.*)$
```
Ensures we’re not matching the `//` after `http:` or `https:`.

---

### 654. Python “`import from`” Lines: `from module import something`
```regex
^\s*from\s+\w+(\.\w+)*\s+import\s+[\w,\s]+$
```
Captures typical import statements.

---

### 655. Capture Eagerly Until `;` or End of String
```regex
^[^;]*;?
```
Matches up to the first semicolon or entire line if none.

---

### 656. Node `require.resolve(...)`
```regex
require\.resolve\s*\(\s*['"][^'"]+['"]\s*\)
```
Find usage of `require.resolve`.

---

### 657. Simple GraphQL Field Definition: `fieldName: Type`
```regex
^\s*[a-zA-Z_]\w*\s*:\s*[A-Z][A-Za-z0-9_]*\s*$
```
Captures a field: type line.

---

### 658. Simple ASCII Emoticons: `:-)` or `:-(`
```regex
:\-[\)\(]
```
Matches basic emoticons.

---

### 659. SystemVerilog `parameter` Declaration
```regex
^\s*parameter\s+\w+\s*=\s*[^;]+;\s*$
```
Captures a single-line parameter statement.

---

### 660. Lines With at Least 3 Commas
```regex
^([^,]*,){3,}[^,]*$
```
4 or more fields separated by commas.

---

### 661. Basic Slack Command Format `/command arg1 arg2`
```regex
^\/[a-zA-Z0-9_]+(\s+.+)?$
```
Captures slash commands.

---

### 662. Ensure line has “foo” in uppercase “FOO”
```regex
\bFOO\b
```
Strict uppercase match only.

---

### 663. Django Templating Variable: `{{ variable }}` with underscores
```regex
\{\{\s*[A-Za-z_]\w*\s*\}\}
```
Captures `{{ var_name }}`.

---

### 664. Mac-Style CR Endings (No LF)
```regex
\r(?!\n)
```
Find carriage returns not followed by line feed.

---

### 665. Disallow 2 or More Spaces in a Row
```regex
^(?!.* {2,}).*$
```
No double spaces anywhere.

---

### 666. Progressive Web App Manifest `start_url` Key
```regex
"start_url"\s*:\s*"[^"]+"
```
Captures `start_url` property.

---

### 667. N-Triples RDF Statement `<subject> <predicate> <object> .`
```regex
^<[^>]+>\s+<[^>]+>\s+<[^>]+>\s*\.\s*$
```
Simplistic triple with URIs.

---

### 668. Lines That Match a Word Followed by Exactly That Word Reversed
```regex
\b([A-Za-z]+)\b\s+\b\1\b(?R)? 
```
Tricky approach. Simpler version:
```regex
(\w+)\s+\1(?-i)
```
But we want reversed? Another approach:
```regex
(\w+)\s+(\w+)
```
Then check if second is reverse in a separate step. (Regex alone is tough for full reversal checks.)

---

### 669. IPv4 With EXACT 3 Digits in Each Octet
```regex
\b\d{3}\.\d{3}\.\d{3}\.\d{3}\b
```
Even if out of range (like 999.999.999.999).

---

### 670. Lines With `class` but Not the Word `interface`
```regex
^(?=.*\bclass\b)(?!.*\binterface\b).*$
```
Ensures class usage, excludes interface usage.

---

### 671. Balanced `[ [ ] ]` Brackets (Naive, Single Nest Level)
```regex
\[\s*\[[^\]]*\]\s*\]
```
One-level nesting only.

---

### 672. Find a CSS Media Query: `@media (condition) { ... }`
```regex
@media\s*\([^\)]*\)\s*\{[\s\S]*?\}
```
Captures block.

---

### 673. “Line Has a Digit, Then a Hyphen, Then a Digit”
```regex
\d-\d
```
Find something like `4-5`.

---

### 674. Capture 3 or More Consecutive Alphabetic Letters
```regex
[a-zA-Z]{3,}
```
Longer word segments.

---

### 675. ASCII Letters or Quoted Strings
```regex
(?:[A-Za-z]+|"[^"]+")
```
Either plain letters or double-quoted text.

---

### 676. Liquid Template Tag: `{% tag_name ... %}`
```regex
\{\%\s*\w[\w-]*\s+[^%]*\%\}
```
Captures a block tag.

---

### 677. `robots.txt` Disallow Lines: `Disallow: /path`
```regex
^Disallow:\s+\/\S*$
```
Basic rule line in `robots.txt`.

---

### 678. ASCII Digits or Slash Only
```regex
^[0-9/]+$
```
Numbers and slashes.

---

### 679. URL That Ends With `.php`
```regex
https?:\/\/[^?#]+\.php(?:\?[^#]*)?(?:#.*)?$
```
Optional query and fragment.

---

### 680. Match Single or Double `++` or `--` Operators
```regex
(\+\+|--)+
```
One or more increments/decrements in sequence.

---

### 681. AngularJS-Style Expressions: `{{variable}}`
```regex
\{\{\s*[A-Za-z_]\w*\s*\}\}
```
Captures double-curly variable usage.

---

### 682. BASH “here-string” Redirection: `<<< "some text"`
```regex
<<<\s*(['"])[^'"]*\1
```
Finds `<<< "string"` constructs.

---

### 683. Word Repeated With a Slash: `word/word`
```regex
\b([A-Za-z]+)\/\1\b
```
Captures “foo/foo”.

---

### 684. C99 Hex Float Notation: `0x1.fp+2`
```regex
0x[0-9A-Fa-f]+\.[0-9A-Fa-f]+p[+\-]?\d+
```
Captures `hexfloat`.

---

### 685. Single `\r\n` Sequence, Not Repeated
```regex
\r\n(?!\r\n)
```
One CRLF, ensures no second CRLF immediately after.

---

### 686. Lines That Only Contain Characters “X”, “Y”, “Z”
```regex
^[XYZ]*$
```
Empty or any combo of X/Y/Z.

---

### 687. `.apk` Android Package Extension
```regex
^.+\.apk$
```
Matches lines ending with `.apk`.

---

### 688. Rust `impl` Block for a Named Type
```regex
^\s*impl\s+\w+\s+for\s+[A-Z][A-Za-z0-9_]*\s*\{\s*$
```
Captures `impl Trait for Type {`.

---

### 689. Word Followed by `-` Then Numeric ID
```regex
\b[A-Za-z]+\-\d+\b
```
Example: `JIRA-123`.

---

### 690. SQL `$1, $2, ...` Parameter Placeholders
```regex
\$\d+
```
Captures PostgreSQL-style placeholders.

---

### 691. JSON String With Allowed Escapes for `"` or `\`
```regex
"(?:\\["\\\/bfnrt]|\\u[0-9A-Fa-f]{4}|[^"\\])*"
```
RFC 7159–style string escapes (partial coverage).

---

### 692. Indentation of Exactly 2 Spaces (No Tabs)
```regex
^( {2})+
```
Groups of two spaces at line start.

---

### 693. C++ Scoped Enum Declaration: `enum class`
```regex
^\s*enum\s+class\s+\w+
```
Captures lines with `enum class`.

---

### 694. Inverse: Lines That Do Not Contain a Vowel
```regex
^[^aeiouAEIOU]*$
```
Zero vowels only.

---

### 695. Markdown Bold with Double Underscores: `__bold__`
```regex
__([^_]+)__
```
Ignores nesting edge cases.

---

### 696. IP + Slash + 2-Digit Number: `127.0.0.1/32`
```regex
\b\d{1,3}(\.\d{1,3}){3}\/\d{1,2}\b
```
CIDR up to /99 (loose). Adjust as needed.

---

### 697. Capture an Optional Sign Then a Non-Zero Leading Digit (No Leading Zero)
```regex
^[+-]?[1-9]\d*$
```
No leading zero except for “0” itself is excluded.

---

### 698. ReStructuredText Title Overline/Underline
```regex
^=+\r?\n[^\r\n]+\r?\n=+$
```
Captures lines with `===` above and below a title.

---

### 699. HTML Tag Containing “aria-” Attribute
```regex
<\w+\b[^>]*\baria-[a-zA-Z0-9_-]+\s*=\s*(['"])[^'"]*\1[^>]*>
```
Accessibility attribute detection.

---

### 700. Minimal TeX Macro `\command{something}`
```regex
\\[A-Za-z]+\{[^}]*\}
```
Captures a backslash command with braces content.

---


### 701. Match 4+ Consecutive Identical Digits
```regex
(\d)\1{3,}
```
Finds runs of at least four identical digits (e.g., `1111`, `22222`).

---------------------------------------

### 702. Find HTML `<select>` Tags With No `<option>` Inside
```regex
<select\b[^>]*>(?!.*<option\b).*?<\/select>
```
Captures `<select>` elements that do not contain any `<option>` tags.

---------------------------------------

### 703. Match Comma-Separated Integers, Potentially Allowing Spaces
```regex
^\s*\d+(?:\s*,\s*\d+)*\s*$
```
Ensures a line is only integers separated by commas, optionally with spaces.

---------------------------------------

### 704. Capture Microsoft SQL Server `USE [database]` Statements
```regex
^\s*USE\s+\[([^\]]+)\]\s*;\s*$
```
Captures database name inside brackets for a `USE [dbName];` line.

---------------------------------------

### 705. Lines That Contain `eval(` in JavaScript
```regex
\b(eval)\s*\(
```
Finds occurrences of `eval(`, which might be a security concern.

---------------------------------------

### 706. Match a Single `@` Surrounded by Word Characters
```regex
\w@\w
```
Ensures an `@` sign is inside word characters on both sides.

---------------------------------------

### 707. Ternary Operator in JavaScript/TypeScript
```regex
\w+\s*\?\s*[^:]+\s*:\s*[^;]+
```
Finds a basic ternary: `condition ? valueIfTrue : valueIfFalse`.

---------------------------------------

### 708. Match an Incomplete `<img` Tag Missing `>` 
```regex
<img\b[^>]*$
```
Captures lines starting an `<img` but never closing the tag.

---------------------------------------

### 709. Capture H1-Level Markdown Headings With Trailing Hashes
```regex
^# (.+?)(?:\s*#+)?$
```
Finds lines like `# Heading` with optional trailing `###`.

---------------------------------------

### 710. Apache `Require all granted` Directive
```regex
^\s*Require\s+all\s+granted\s*$
```
Captures lines giving open access in Apache config.

---------------------------------------

### 711. Basic `.bash_profile` or `.bashrc` Alias Definition
```regex
^\s*alias\s+[\w-]+\s*=\s*(['"]).*\1\s*$
```
Captures lines defining an alias, e.g., `alias ll='ls -la'`.

---------------------------------------

### 712. Match a Basic UML Relationship Arrow: `A --> B`
```regex
^(\w+)\s*-->\s*(\w+)$
```
Finds lines describing a UML arrow from one entity to another.

---------------------------------------

### 713. Identify `git rebase` Commands in Scripts
```regex
^\s*git\s+rebase\s+.*$
```
Captures lines invoking `git rebase`.

---------------------------------------

### 714. Chinese Characters (CJK Unified Ideographs)
```regex
[\u4E00-\u9FFF]+
```
Matches one or more Chinese (CJK) characters.

---------------------------------------

### 715. CSS `@import url(...)` Statements
```regex
@import\s+url\(\s*(['"])?[^'"]+\1?\s*\)\s*;?
```
Locates CSS imports with `url(...)`.

---------------------------------------

### 716. Detect Basic `pip install package==version`
```regex
^\s*pip\s+install\s+\S+==\S+$
```
Finds lines installing a specific version with `pip`.

---------------------------------------

### 717. Match Key-Value Pair in JSON Where Value Is an Array
```regex
"([^"]+)"\s*:\s*\[\s*[^]]*\]
```
Captures `"key": [ ... ]` structures.

---------------------------------------

### 718. HTML `data-test="..."` Attributes
```regex
data-test\s*=\s*(['"])(.*?)\1
```
Captures testing attributes often used for automated tests.

---------------------------------------

### 719. Basic IPv4 Without Leading Zeroes in Octets (1-3 Digits, But Not 0xx)
```regex
\b((25[0-5]|2[0-4]\d|[1]?\d?\d)\.){3}(25[0-5]|2[0-4]\d|[1]?\d?\d)\b
```
Prevents octets like `00` or `01`. (Similar to some patterns, but ensures no leading zeroes if more than one digit.)

---------------------------------------

### 720. Detect a `.tar.gz` or `.tgz` File Extension
```regex
^.+\.(?:tar\.gz|tgz)$
```
Matches common compressed archive filenames.

---------------------------------------

### 721. Parse Apache or Nginx Error Log `client:` IP Segment
```regex
client:\s*(\b\d{1,3}(\.\d{1,3}){3}\b)
```
Captures IP after `client:` in log lines.

---------------------------------------

### 722. Basic Matching of an ASCII Signature Block `-----BEGIN TEXT----- ... -----END TEXT-----`
```regex
^-+BEGIN [A-Z ]+-+[\s\S]*?-+END [A-Z ]+-+$
```
Captures typical ASCII armor or textual blocks with a custom label.

---------------------------------------

### 723. Windows Environment Variable Reference `%VAR%`
```regex
%[A-Za-z0-9_]+%
```
Finds references like `%USERNAME%` or `%PATH%` in Windows scripts.

---------------------------------------

### 724. Unsigned 32-bit Integer Range (0–4294967295)
```regex
^(?:[0-9]|[1-9]\d{1,9}|4[0-1]\d{8}|42[0-8]\d{7}|429[0-3]\d{6}|4294[0-8]\d{5}|42949[0-5]\d{4}|429496[0-6]\d{3}|4294967[0-1]\d{2}|42949672[0-8]\d|429496729[0-5])$
```
Checks a string is within [0..4294967295]. (Large but it’s a numeric boundary regex.)

---------------------------------------

### 725. Lines With `<style scoped>` HTML Tag
```regex
<style\b[^>]*\bscoped\b[^>]*>([\s\S]*?)<\/style>
```
Captures `<style scoped>` sections in HTML (used in Vue.js Single File Components).

---------------------------------------

### 726. Basic Dart `part of` Declaration
```regex
^\s*part\s+of\s+[A-Za-z_]\w*(?:\.[A-Za-z_]\w*)*;\s*$
```
Finds a `part of library.name;` line in Dart.

---------------------------------------

### 727. GRUB Configuration `menuentry` Lines
```regex
^\s*menuentry\s+['"].+['"]\s*\{$
```
Captures lines in `grub.cfg` that define a boot menu entry.

---------------------------------------

### 728. Python `yield from` Statement
```regex
^\s*yield\s+from\s+\S+
```
Identifies `yield from iterable` usage in Python.

---------------------------------------

### 729. Match an IRC Channel Name (e.g., `#channel`)
```regex
^#[A-Za-z0-9][A-Za-z0-9_\-]{0,49}$
```
Channels typically start with `#`, up to 50 chars in some networks.

---------------------------------------

### 730. Docker `EXPOSE` Instruction With Port/Protocol
```regex
^EXPOSE\s+\d+\/(tcp|udp)\s*$
```
Captures a line like `EXPOSE 80/tcp`.

---------------------------------------

### 731. JSON “Key”: Boolean
```regex
"([^"]+)"\s*:\s*(?:true|false)
```
Finds boolean values for a JSON key.

---------------------------------------

### 732. Pydantic Field Definition in Python
```regex
^\s*[A-Za-z_]\w*\s*:\s*[\w\[\],]+\s*=\s*Field\(.*\)
```
Captures lines like `age: int = Field(..., gt=0)`.

---------------------------------------

### 733. `.editorconfig` Key-Value Lines
```regex
^\s*[A-Za-z0-9._-]+\s*=\s*.+$
```
Matches lines defining `.editorconfig` properties, e.g. `indent_style = space`.

---------------------------------------

### 734. `npm run` Script Command
```regex
^\s*npm\s+run\s+\S+
```
Captures lines invoking an `npm run script`.

---------------------------------------

### 735. Lines That Are Only an Equals Sign or Dashes (Used in Some Docs)
```regex
^(={3,}|-{3,})$
```
Matches lines of 3+ equals or 3+ dashes. For ASCII doc headings or separators.

---------------------------------------

### 736. Palindromic 5-Digit Number
```regex
^(\d)(\d)\d\2\1$
```
Ensures a 5-digit palindrome, e.g., `12321`, `95459`.

---------------------------------------

### 737. Basic Valid Twitter URL
```regex
^https?:\/\/(www\.)?twitter\.com\/[A-Za-z0-9_]{1,15}\/?$
```
Ensures user profile link like `https://twitter.com/username`.

---------------------------------------

### 738. HTML Comment Without a Space After `<!--`
```regex
<!--[^ >].*?-->
```
Roughly finds comments that begin with `<!--` but no space after it.

---------------------------------------

### 739. Python-Style Single-Line Docstring `"""something"""` in One Line
```regex
"""[^"\r\n]+"""
```
Captures one-line triple-double-quoted docstrings.

---------------------------------------

### 740. IP-Like Patterns in Square Brackets: `[192.168.1.1]`
```regex
\[\d{1,3}(\.\d{1,3}){3}\]
```
Finds IPv4-like addresses in square brackets (not validated for range).

---------------------------------------

### 741. C/C++ `while(condition);` Shortcut
```regex
^\s*while\s*\([^)]*\)\s*;\s*$
```
Captures lines with empty while loops.

---------------------------------------

### 742. CSV Fields With a Semicolon Separator
```regex
([^;]+)(?:;|$)
```
Split on semicolons for certain locales.

---------------------------------------

### 743. JSON String That Might Contain `\u` Escapes
```regex
"([^"\\]|\\["\\/bfnrt]|\\u[0-9A-Fa-f]{4})*"
```
More complete JSON string pattern, including `\uXXXX`.

---------------------------------------

### 744. UNIX `groups` Command Output Format
```regex
^\w+(?:\s*:\s*)(\w+(?:\s+\w+)*)?$
```
Captures optional group list after username: `user : group1 group2`.

---------------------------------------

### 745. Look for File Creation in OpenSSL Output: `Generating RSA private key`
```regex
Generating\s+RSA\s+private\s+key
```
Simple detection in logs.

---------------------------------------

### 746. Basic `@media screen and (max-width: 600px)` Check
```regex
@media\s+screen\s+and\s*\(\s*max-width\s*:\s*\d+px\s*\)
```
Checks a typical media query for small screens.

---------------------------------------

### 747. Arduino-Style Function Prototypes
```regex
^\s*\w+\s+\w+\([^)]*\)\s*;\s*$
```
Captures lines like `void setup();`.

---------------------------------------

### 748. Relative URL Paths With `./` or `../`
```regex
(\.\.?\/)+\S*
```
Finds references to relative paths.

---------------------------------------

### 749. HTML Tag With `placeholder` Attribute (Forms)
```regex
<\w+\b[^>]*\bplaceholder\s*=\s*(['"]).*?\1
```
Captures placeholders in inputs or textareas.

---------------------------------------

### 750. Hexadecimal Numbers Larger Than `0xFFFF`
```regex
0x[1-9A-Fa-f][0-9A-Fa-f]{4,}
```
Requires more than 4 hex digits.

---------------------------------------

### 751. URL With `ftp://`
```regex
^ftp:\/\/[^\s\/]+(?:\/[^\s]*)?$
```
Capture basic FTP URLs.

---------------------------------------

### 752. YAML Tag with `!` and Type Name
```regex
^!\w+
```
Identifies lines that start with a custom YAML tag like `!MyTag`.

---------------------------------------

### 753. Captures an R `library(package)` Statement
```regex
^\s*library\s*\(\s*([A-Za-z][A-Za-z0-9._]*)\s*\)
```
Find lines loading an R package.

---------------------------------------

### 754. JSON Bare Number (No quotes)
```regex
:\s*(-?\d+(?:\.\d+)?(?:[eE][+\-]?\d+)?)
```
Captures numeric JSON values after `:` ignoring quotes.

---------------------------------------

### 755. `<link rel="stylesheet" href="...">`
```regex
<link\b[^>]*\brel\s*=\s*(['"])stylesheet\1\b[^>]*>
```
Finds typical CSS link tags.

---------------------------------------

### 756. Lines That Contain a Sequence Like `(foo = bar)`
```regex
\(\s*\w+\s*=\s*\w+\s*\)
```
Captures parentheses with `key = value` inside.

---------------------------------------

### 757. Python Decorators With Arguments: `@decorator(param=val)`
```regex
^@\w+(?:\(\s*\w+\s*=\s*\w+\s*(?:,\s*\w+\s*=\s*\w+)*\))?\s*$
```
Matches `@decorator(...)` lines.

---------------------------------------

### 758. ExtJS or Sencha Class Definition: `Ext.define("...")`
```regex
Ext\.define\(\s*(['"])[^'"]+\1\s*,\s*\{
```
Finds lines that define a new ExtJS class.

---------------------------------------

### 759. Balanced Triple Curly Braces `{{{ }}}` (No Nesting Check)
```regex
\{\{\{[^}]*\}\}\}
```
Captures text enclosed in triple braces.

---------------------------------------

### 760. PGSQL `COMMENT ON TABLE table_name IS '...'`
```regex
^COMMENT\s+ON\s+TABLE\s+\w+\s+IS\s+('([^']*)');$
```
Locates statements to comment on a table.

---------------------------------------

### 761. Labeled Break in Java/C++: `label: break label;`
```regex
^\s*\w+\s*:\s*break\s+\w+\s*;\s*$
```
Captures labeled break statements.

---------------------------------------

### 762. Bash Function: `function name { ... }`
```regex
^\s*function\s+[A-Za-z_]\w*\s*\{.*$
```
Finds one form of bash function definition.

---------------------------------------

### 763. Rust Macro Call `println!()`
```regex
\bprintln!\s*\([^)]*\)
```
Captures macro usage like `println!("Hello {}", name)`.

---------------------------------------

### 764. .NET `var` Declaration in C#
```regex
^\s*var\s+\w+\s*=\s*[^;]+;\s*$
```
Captures lines like `var x = 5;`.

---------------------------------------

### 765. Basic JSON `null` Value
```regex
:\s*null
```
Find `null` assigned after a colon.

---------------------------------------

### 766. HTML Input With `type="checkbox"`
```regex
<input\b[^>]*\btype\s*=\s*(['"])checkbox\1[^>]*>
```
Captures checkbox form elements.

---------------------------------------

### 767. Lines With an Indentation of 2 or 3 Spaces but Not 4
```regex
^(?: {2}| {3})\S.*$
```
Allows lines starting with exactly 2 or 3 spaces but excludes 4.

---------------------------------------

### 768. ISO 8601 Year-Month Only: `YYYY-MM`
```regex
^\d{4}-\d{2}$
```
Captures `2025-03` style strings (no day).

---------------------------------------

### 769. Filenames That Start With a Dot But Are Not `.` or `..`
```regex
^\.(?!\.)([^\/]+)$
```
Hidden files in UNIX, excluding `.` and `..`.

---------------------------------------

### 770. Simple IPv4 in Dot Notation With Optional Subnet `/\d{1,2}`
```regex
\b\d{1,3}(\.\d{1,3}){3}(?:\/(?:[0-2]\d|3[0-2]|[1-9]))?\b
```
Allows a CIDR up to `/32`.

---------------------------------------

### 771. Golang `switch` Statement
```regex
^\s*switch\s+.*\{\s*$
```
Captures lines that begin a Go `switch {`.

---------------------------------------

### 772. Basic Ternary Operator in C-Like Language
```regex
\?\s*[^:]+\s*:\s*[^;]+
```
Finds `? :` usage in a single expression.

---------------------------------------

### 773. `lein` Commands for Clojure
```regex
^lein\s+\S+
```
Captures lines calling `lein something`.

---------------------------------------

### 774. Repeated Word With a Slash in Between: `word/word word/word`
```regex
\b(\w+)\/\1\b
```
Like `test/test`.

---------------------------------------

### 775. Matches for `<hr>` or `<hr color="...">` Variation
```regex
<hr\b[^>]*>
```
Captures horizontal rule tags with or without attributes.

---------------------------------------

### 776. Python Namedtuple Declaration
```regex
^\s*\w+\s*=\s*namedtuple\(\s*(['"])\w+\1\s*,\s*\[?[^]]*\]?\)
```
Identifies lines such as `Point = namedtuple("Point", ["x", "y"])`.

---------------------------------------

### 777. Match a `try { ... } catch() { ... }` in Java/C#
```regex
try\s*\{[^}]*\}\s*catch\s*\([^)]*\)\s*\{[^}]*\}
```
Quickly finds try/catch blocks (no multiline coverage here, just single-line or minimal).

---------------------------------------

### 778. VLAN Interface Notation: `eth0.100`
```regex
^[A-Za-z0-9]+(?:\.[0-9]+)+$
```
Captures typical interface name with VLAN ID (like `eth0.10`).

---------------------------------------

### 779. Single Quoted Strings That Might Have Double Single Quotes for Escapes
```regex
'([^']|'')*'
```
Matches `'O''Reilly'` style escapes.

---------------------------------------

### 780. Basic `import <module>` in a C++ Template 
```regex
^\s*import\s+<[\w\/.]+>\s*;\s*$
```
C++20 modules syntax for header imports.

---------------------------------------

### 781. Consecutive Alphabetic Chunks of Length Exactly 2
```regex
\b[A-Za-z]{2}\b
```
Matches two-letter words or tokens.

---------------------------------------

### 782. SEO Meta Name Tag: `<meta name="keywords" content="...">`
```regex
<meta\s+name\s*=\s*(['"])keywords\1\s+content\s*=\s*(['"])(.*?)\2[^>]*>
```
Captures keywords meta tag.

---------------------------------------

### 783. Basic COBOL `IDENTIFICATION DIVISION.`
```regex
^\s*IDENTIFICATION\s+DIVISION\.\s*$
```
Finds a COBOL ID division line.

---------------------------------------

### 784. Rsyslog `$AllowedSender ...` Directives
```regex
^\s*\$AllowedSender\s+.*$
```
Simple match for lines in `rsyslog.conf`.

---------------------------------------

### 785. Check if a File is a `.exe` or `.dll`
```regex
^.+\.(?:exe|dll)$
```
Captures Windows binaries by extension.

---------------------------------------

### 786. Python `return` With a Tuple
```regex
^\s*return\s+\([^)]*\)
```
Find lines returning a parenthesized tuple.

---------------------------------------

### 787. Match `MACRO:` Lines in a DSL
```regex
^MACRO:\s+\S+
```
Captures lines starting with `MACRO:` plus a token.

---------------------------------------

### 788. Log Messages with `INFO:` or `ERROR:` or `DEBUG:` in Caps
```regex
^(?:INFO|ERROR|DEBUG):\s+.*$
```
Matches lines in a log with known severity levels.

---------------------------------------

### 789. Git Subtree Merge: `git subtree merge --prefix=`
```regex
^\s*git\s+subtree\s+merge\s+--prefix=\S+
```
Captures subtree merges.

---------------------------------------

### 790. Lines With Non-ASCII Letters Only (No ASCII Letters)
```regex
^[^\x00-\x7F]+$
```
Ensures the line is purely beyond ASCII range, ignoring numbers/punctuation.

---------------------------------------

### 791. Java `private static final` Field Declaration
```regex
^\s*private\s+static\s+final\s+\w+(\[\])?\s+\w+\s*=.*;$
```
Captures constants in Java code.

---------------------------------------

### 792. Titles in an `.ini` File with a Semicolon Comment
```regex
^\[([^\]]+)\]\s*(;.*)?$
```
Optionally allows a `; comment` after the section line.

---------------------------------------

### 793. Node.js `require('fs')` or `require("fs")`
```regex
require\s*\(\s*['"]fs['"]\s*\)
```
Captures Node’s built-in `fs` import usage.

---------------------------------------

### 794. Slack Bot Command: `/command something --option`
```regex
^\/[a-zA-Z0-9_]+(\s+[^-]+)?(\s+--[a-zA-Z0-9_-]+)?$
```
Very rough capture of a slash command with an optional option.

---------------------------------------

### 795. Text Surrounded by `(())` Double Parentheses
```regex
\(\(([^()]*)\)\)
```
Captures content in double parentheses `((...))`.

---------------------------------------

### 796. SNMP OID Notation: `1.3.6.1.4.1.`
```regex
^(\d+\.)+\d+$
```
Matches dotted numeric OID sequences.

---------------------------------------

### 797. Simple Ruby `rescue => e` Clause
```regex
rescue\s*=>\s*\w+
```
Find lines `rescue => ex`.

---------------------------------------

### 798. Email Address With `+` Tag and a Specific TLD (e.g., `.io`)
```regex
^[A-Za-z0-9._%+-]+(\+[A-Za-z0-9._%+-]+)?@[A-Za-z0-9.-]+\.io$
```
Restricts the TLD to `.io`.

---------------------------------------

### 799. Match "TODO" in All Caps Surrounded by Non-Word or Start/End
```regex
(^|\W)TODO($|\W)
```
Ensures `TODO` is recognized as a separate token.

---------------------------------------

### 800. `php.ini` Directive: `key = "value"`
```regex
^\s*\w+\s*=\s*(?:"[^"]*"|'[^']*'|\S+)\s*$
```
Captures lines in `php.ini` style.

---------------------------------------

### 801. Lines With a CSS `border:` Property
```regex
border\s*:\s*[^;]+;
```
Finds `border: ...;` lines in CSS.

---------------------------------------

### 802. Golang Interface Definition
```regex
type\s+[A-Za-z_]\w*\s+interface\s*\{[^}]*\}
```
Captures lines defining a Go interface block.

---------------------------------------

### 803. Mac OS X `plutil` Command in a Script
```regex
^\s*plutil\s+-[a-zA-Z]+\s+.*$
```
Find lines with `plutil -convert`, etc.

---------------------------------------

### 804. Markdown Horizontal Rule With Asterisks
```regex
^\*{3,}\s*$
```
A line of three or more `*` is often a horizontal rule in Markdown.

---------------------------------------

### 805. Pom.xml `<dependency>` Tag
```regex
<dependency>\s*<groupId>[^<]+<\/groupId>\s*<artifactId>[^<]+<\/artifactId>\s*<version>[^<]+<\/version>\s*<\/dependency>
```
Captures a minimal Maven dependency block.

---------------------------------------

### 806. Strict 8-Digit Hex (No 0x Prefix)
```regex
^[A-Fa-f0-9]{8}$
```
A single 32-bit hex value without prefix.

---------------------------------------

### 807. Wireshark Filter-Like `ip.addr == 192.168.x.x`
```regex
^ip\.addr\s*==\s*\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}$
```
Very simplistic approach for an IP filter.

---------------------------------------

### 808. Lines With `Option Explicit` or `Option Strict` in VB.NET
```regex
^\s*Option\s+(Explicit|Strict)\s+On\s*$
```
Captures the line enabling these options.

---------------------------------------

### 809. Facebook Profile/Page URL
```regex
^https?:\/\/(www\.)?facebook\.com\/[A-Za-z0-9.]+\/?$
```
Allows standard FB URLs with username or page ID.

---------------------------------------

### 810. Plural `ies` to singular: find words ending in `ies`
```regex
\bies\b
```
Then you might replace with `y` in certain editors, but it’s just the find pattern here.

---------------------------------------

### 811. `.class` File Names (Java bytecode)
```regex
^[^\\/:*?"<>|]+\.class$
```
Captures valid Java `.class` filenames (no directories).

---------------------------------------

### 812. Docker Compose `version: "3"` Lines
```regex
^\s*version\s*:\s*['"]3(\.\d+)?['"]\s*$
```
Find `version: "3"` or `version: "3.8"` lines in docker-compose.

---------------------------------------

### 813. Windows Drive Mapping `net use X: \\server\share`
```regex
^\s*net\s+use\s+[A-Za-z]:\s+\\\\[^\s]+
```
Captures basic net use commands.

---------------------------------------

### 814. Basic Parametric Equation Form: `x(t) = ... ; y(t) = ...`
```regex
^[xy]\(t\)\s*=\s*[^;]+;\s*$
```
Captures lines `x(t) = expression;` or `y(t) = expression;`.

---------------------------------------

### 815. PostgreSQL Copy Statement With Delimiter
```regex
^COPY\s+\w+(\.\w+)?\s+FROM\s+[^']+'[^']+'(?:\s+DELIMITER\s+'[^']+')?.*;$
```
Rough match for `COPY table FROM 'file' DELIMITER ',';`.

---------------------------------------

### 816. Unquoted JSON-Like Key in Some Dev Tools
```regex
^\s*\w+\s*:\s*.+$
```
Find lines that look like `key: value`.

---------------------------------------

### 817. AppleScript `tell application "Finder"` 
```regex
^\s*tell\s+application\s+(['"])Finder\1
```
Captures lines referencing Finder in AppleScript.

---------------------------------------

### 818. Lines With `sendmail -t`
```regex
^\s*sendmail\s+-t\s+
```
Identifies usage of `sendmail -t`.

---------------------------------------

### 819. Quick Check for HTML: `<html> ... </html>` in One Line
```regex
<\s*html\s*>.*<\s*\/html\s*>
```
A single-line HTML check.

---------------------------------------

### 820. `Sub`/`End Sub` in VBA
```regex
^\s*Sub\s+\w+\s*\(.*\)\s*|^\s*End\s+Sub\s*$
```
Captures lines starting or ending a VBA Subroutine.

---------------------------------------

### 821. CSS `box-shadow:` Property
```regex
box-shadow\s*:\s*[^;]+;
```
Find box-shadow definitions in CSS.

---------------------------------------

### 822. Email Lines That Start With `>` Quoting
```regex
^>+.*$
```
Captures typical email quote lines.

---------------------------------------

### 823. Basic AngularJS `ng-` Attributes
```regex
\bng-[a-zA-Z-]+\s*=\s*(['"])[^'"]*\1
```
Find attributes like `ng-model="..."`, `ng-click="..."`.

---------------------------------------

### 824. Python Dictionary Definition With Braces
```regex
^\s*\w+\s*=\s*\{[^}]*\}
```
Captures lines like `my_dict = { 'key': 'value' }`.

---------------------------------------

### 825. Regular Expression for `REG ADD` in Windows
```regex
^REG\s+ADD\s+("[^"]+"|\w+:\\[^\s]+)\s+\/v\s+\w+\s+\/t\s+\w+\s+\/d\s+.*$
```
Captures a `REG ADD Key /v Value /t Type /d Data` line.

---------------------------------------

### 826. Lines Ending With a Plus Sign `+`
```regex
\+$
```
Identifies lines that end with `+`.

---------------------------------------

### 827. Python Format-Style Placeholders: `%s`, `%d`
```regex
%[sdifouxXeEgG]
```
Catches older Python `%` formatting placeholders.

---------------------------------------

### 828. Basic Swift Struct Declaration
```regex
^\s*struct\s+[A-Za-z_]\w*\s*\{\s*$
```
Captures lines that declare a Swift struct.

---------------------------------------

### 829. Lines Containing Only Braces and Semicolons (C/C++ Minimization)
```regex
^[{};]*$
```
Empty code blocks or just semicolons.

---------------------------------------

### 830. LaTeX `\cite{...}` Reference
```regex
\\cite\{[^}]+\}
```
Finds citation references in TeX.

---------------------------------------

### 831. Joomla-Style `JFactory::getApplication()` Call
```regex
JFactory::getApplication\s*\(\)
```
Captures usage of Joomla’s global app factory method.

---------------------------------------

### 832. `xz` Compressed File: `.tar.xz`
```regex
^.+\.tar\.xz$
```
Matches `.tar.xz` file extension.

---------------------------------------

### 833. Symbolic Links in `ls -l` Output `lrwxrwxrwx`
```regex
^l[rwxsStT-]{9}\s+
```
Identifies lines describing a symlink in a long listing.

---------------------------------------

### 834. Lines With a Leading `;` (INI or config Comments)
```regex
^;\s*.*$
```
Captures semicolon-based comment lines.

---------------------------------------

### 835. JavaScript `class` With an `extends`
```regex
^\s*class\s+\w+\s+extends\s+\w+\s*\{\s*$
```
Matches lines that define a subclass.

---------------------------------------

### 836. Capture “functionName(arg1,arg2)” Without Whitespace
```regex
\b\w+\([^,\)]+(?:,[^,\)]+)*\)
```
Ensures arguments are not spaced, e.g. `func(a,b)`.

---------------------------------------

### 837. HTML Anchor With `rel="noopener"` or `rel="noreferrer"`
```regex
<a\b[^>]*\brel\s*=\s*(['"])(?:noopener|noreferrer)\1[^>]*>
```
Captures secure link rel usage.

---------------------------------------

### 838. Basic `@property` in Objective-C
```regex
^\s*@property\s*\(.*\)\s+\w+\s+\*?\w+\s*;$
```
Locates typical property lines in Obj-C.

---------------------------------------

### 839. YAML Key That Includes a Dot: `key.subkey: value`
```regex
^[A-Za-z0-9_.-]+\s*:\s*.+$
```
Captures lines in YAML with dotted keys.

---------------------------------------

### 840. Docker `HEALTHCHECK` Instruction
```regex
^HEALTHCHECK\s+.*$
```
Captures any line starting with `HEALTHCHECK`.

---------------------------------------

### 841. Inno Setup `AppName=...`
```regex
^AppName\s*=\s*.+$
```
Find lines specifying the application name in Inno Setup script.

---------------------------------------

### 842. Windows `.cmd` File Shebang-Like: `::#`
```regex
^::#
```
Some scripts use `::#` to mimic a shebang in `.cmd` or `.bat`.

---------------------------------------

### 843. ICU MessageFormat Placeholder: `{0}, {1}`
```regex
\{\d+\}
```
Captures placeholders like `{0}`, `{1}`, etc.

---------------------------------------

### 844. C/C++ Macro Definition With Continuation Backslash
```regex
^#define\s+\w+\s+\\$
```
Matches a line that ends with `\` for multi-line macro.

---------------------------------------

### 845. Lines Containing Only Binary Zeros: `\x00` Repetitions
```regex
^(?:\x00+)$
```
Pure null bytes line (depending on editor support).

---------------------------------------

### 846. Java `enum` Declaration
```regex
^\s*public?\s*enum\s+\w+\s*\{\s*$
```
Captures the start of an enum block.

---------------------------------------

### 847. Slack `<mailto:...|...>` Link
```regex
<mailto:[^|>]+\|[^>]+>
```
Captures Slack email link syntax.

---------------------------------------

### 848. Python Class With a Single Inheritance
```regex
^\s*class\s+\w+\(\w+\)\s*:\s*$
```
Matches `class Child(Parent):`.

---------------------------------------

### 849. HTML `<video>` Tag With `autoplay`
```regex
<video\b[^>]*\bautoplay\b[^>]*>
```
Captures video tags that autoplay.

---------------------------------------

### 850. IPv6 Without Abbreviation (Full 8 Groups)
```regex
^([0-9A-Fa-f]{1,4}:){7}[0-9A-Fa-f]{1,4}$
```
A complete, uncompressed IPv6 address form.

---------------------------------------

### 851. Puppet `class { 'name': }` Resource
```regex
class\s*\{\s*(['"])\w+(\.\w+)*\1\s*:\s*\}
```
Captures a bare Puppet class resource.

---------------------------------------

### 852. Matches `q()`, `qq()`, `qw()`, `qx()` in Perl
```regex
\bq[wx]?\(.*?\)
```
Finds Perl quote-like operators.

---------------------------------------

### 853. IPv4 With Dot But Possibly Missing Some Octets (like `127.0`)
```regex
^\d{1,3}(\.\d{1,3}){1,3}$
```
Allows 2-4 segments.

---------------------------------------

### 854. CSS `@font-face` Rule
```regex
@font-face\s*\{\s*[^}]*\}
```
Locates a font-face block in CSS.

---------------------------------------

### 855. Python `.format()` Method: `"{} {}".format(...)`
```regex
\.\s*format\s*\(
```
Captures use of `.format(` on a string or variable.

---------------------------------------

### 856. Lines With `#if` or `#endif` in C Preprocessor
```regex
^#\s*(?:if|endif)\b
```
Finds conditional compilation lines.

---------------------------------------

### 857. Rails `belongs_to :model`
```regex
^\s*belongs_to\s+:\w+
```
Captures a typical Rails association.

---------------------------------------

### 858. Terraform Resource Declaration
```regex
^\s*resource\s+"[^"]+"\s+"[^"]+"\s*\{
```
Find lines like `resource "aws_instance" "example" {`.

---------------------------------------

### 859. Microsoft Excel Range Notation: `A1:C10`
```regex
^[A-Z]+\d+:[A-Z]+\d+$
```
Captures a range in typical spreadsheet format.

---------------------------------------

### 860. `.htpasswd` Format: `username:encrypted`
```regex
^[^:]+:.+$
```
Matches lines with `user:hash`.

---------------------------------------

### 861. Basic AWS ARN `arn:aws:service:region:accountId:resource`
```regex
^arn:aws:[a-z0-9-]+:[a-z0-9-]*:\d{12}:.+$
```
Captures a typical AWS ARN structure.

---------------------------------------

### 862. Hibernate/JPA Annotation: `@Entity`
```regex
^@\s*Entity\s*$
```
Find lines marking an entity class in Java.

---------------------------------------

### 863. Hex Strings of Length 3 or 6 (Without `#`)
```regex
^[A-Fa-f0-9]{3}$|^[A-Fa-f0-9]{6}$
```
Matches 3 or 6 hex digits plainly.

---------------------------------------

### 864. File Path in Single Quotes on Unix: `'./some/dir'`
```regex
'(\./[^']*)'
```
Captures a relative path in single quotes.

---------------------------------------

### 865. `lua` Function Definition: `function name(...)`
```regex
^\s*function\s+\w+\s*\([^)]*\)\s*$
```
A typical single-line function declaration in Lua.

---------------------------------------

### 866. Basic RSpec Test in Ruby: `it "does something" do`
```regex
^\s*it\s+(['"]).*\1\s+do\s*$
```
Captures `it "description" do`.

---------------------------------------

### 867. HTML `<meta http-equiv="refresh">`
```regex
<meta\s+http-equiv\s*=\s*(['"])refresh\1\s+content\s*=\s*(['"])[^'"]*\2[^>]*>
```
Finds meta refresh tags.

---------------------------------------

### 868. TOML Table Header `[table.subtable]`
```regex
^\[[A-Za-z0-9_.-]+\]$
```
Captures bracketed table headers in TOML.

---------------------------------------

### 869. Bash Arithmetic Expression: `$[ expression ]` (Obsolete)
```regex
\$\[[^\]]*\]
```
Matches old `$[...]` expansions.

---------------------------------------

### 870. Simple Babel/ESLint Comment `/* eslint-disable */`
```regex
^/\*\s*eslint-[a-z-]+\s*\*/$
```
Captures lines disabling ESLint.

---------------------------------------

### 871. PostgreSQL `$1`, `$2`, `$n` Placeholders With Curly Braces
```regex
\$\{\d+\}
```
Some frameworks represent placeholders as `${1}`, `${2}`.

---------------------------------------

### 872. Swift Protocol Declaration
```regex
^\s*protocol\s+[A-Za-z_]\w*\s*\{\s*$
```
Captures lines declaring a Swift protocol.

---------------------------------------

### 873. HTML Tag with a `pattern` Attribute (Forms)
```regex
<\w+\b[^>]*\bpattern\s*=\s*(['"])[^'"]*\1
```
Locates form elements with a `pattern` regex attribute.

---------------------------------------

### 874. Double Quoted JSON Key Without Trailing Whitespace
```regex
^"[^"]+"\s*:
```
Captures a JSON key at start of line.

---------------------------------------

### 875. Captures a “for each” in VBScript: `For Each var In collection`
```regex
^\s*For\s+Each\s+\w+\s+In\s+\w+\s*$
```
Simple VBScript loop line.

---------------------------------------

### 876. grep Output With “Binary file (filename) matches”
```regex
^Binary\s+file\s+[^)]+\)\s+matches\s*$
```
Identifies grep’s “Binary file” match line.

---------------------------------------

### 877. Lines With `+OK` or `-ERR` (POP3 or IMAP)
```regex
^(?:\+OK|\-ERR).*$
```
Captures protocol response lines.

---------------------------------------

### 878. Basic YAML Key That Must Start With a Letter
```regex
^[A-Za-z][A-Za-z0-9_-]*:\s*.*$
```
Ensures the key starts with a letter.

---------------------------------------

### 879. Kotlin Function With Receiver Type: `fun String.foo()`
```regex
^fun\s+[A-Za-z_]\w*\.\w+\s*\([^)]*\)
```
Captures extension functions like `fun String.myFunc()`.

---------------------------------------

### 880. MATLAB `for` Loop: `for i=1:10`
```regex
^\s*for\s+\w+\s*=\s*\d+\s*:\s*\d+
```
Basic iteration in MATLAB.

---------------------------------------

### 881. Lines That Are Exactly Two Quoted Strings
```regex
^"[^"]+"\s+"[^"]+"$
```
No extra text.

---------------------------------------

### 882. SNMP Community Strings Like `community public ro`
```regex
^\s*community\s+\S+\s+(?:rw|ro)\s*$
```
Simple pattern for SNMP community lines.

---------------------------------------

### 883. `.proto` File `message` Declaration
```regex
^\s*message\s+\w+\s*\{\s*$
```
Captures `message Foo {` in Protobuf.

---------------------------------------

### 884. CSV Row That Might Contain Quoted Fields With Semicolon
```regex
"[^"]*"|[^";]+
```
Alternate semicolon-based CSV approach.

---------------------------------------

### 885. Emacs Lisp `defun` Definition
```regex
^\s*\(defun\s+\w+\s*\([^)]*\)
```
Captures lines that define an Emacs Lisp function.

---------------------------------------

### 886. Angular HTML `*ngIf`
```regex
\*ngIf\s*=\s*(['"])[^'"]*\1
```
Finds `*ngIf="condition"` in templates.

---------------------------------------

### 887. Node Inspect Brk Flag: `node --inspect-brk`
```regex
^node\s+--inspect-brk\b
```
Captures usage for debugging Node.

---------------------------------------

### 888. Freeform JSON Array With Objects Inside
```regex
\[\s*\{\s*[^}]*\}\s*(,\s*\{\s*[^}]*\}\s*)*\]
```
Roughly finds `[ { ... }, { ... } ]`.

---------------------------------------

### 889. Dockerfile `LABEL key="value"`
```regex
^LABEL\s+[\w.-]+\s*=\s*(['"]).*?\1
```
Captures a single Docker label statement.

---------------------------------------

### 890. `npm uninstall` Command
```regex
^\s*npm\s+uninstall\s+\S+
```
Lines removing a package.

---------------------------------------

### 891. Apple .DS_Store Files
```regex
^\.DS_Store$
```
Matches hidden macOS resource file.

---------------------------------------

### 892. Jenkins Pipeline `node { ... }`
```regex
node\s*\{\s*[^}]*\}
```
Captures a Jenkins pipeline block.

---------------------------------------

### 893. `pip freeze` Output Lines
```regex
^[A-Za-z0-9._-]+==[^\s]+$
```
Identifies pinned packages in `requirements.txt`.

---------------------------------------

### 894. Python Triple-Quoted Raw String `r""" ... """` (Single-Line)
```regex
r""".*?"""
```
Matches a raw triple-quoted string on one line.

---------------------------------------

### 895. JSON “key”: [ { ... }, { ... } ]
```regex
"([^"]+)"\s*:\s*\[\s*\{[^}]*\}\s*(,\s*\{[^}]*\}\s*)*\]
```
Finds arrays of objects assigned to a key.

---------------------------------------

### 896. Lines Starting With `sudo rm -rf`
```regex
^sudo\s+rm\s+-rf\b
```
Potentially destructive command detection.

---------------------------------------

### 897. `.scss` Variables `$var: value;`
```regex
^\s*\$\w+\s*:\s*[^;]+;\s*$
```
Captures Sass/SCSS variable assignments.

---------------------------------------

### 898. HTML Tag with a Custom `on` Handler: `onCustom=...`
```regex
<\w+\b[^>]*\bon[A-Z][A-Za-z]+\s*=\s*(['"]).*?\1[^>]*>
```
Finds an `onSomething=` attribute (beyond standard onClick, etc.).

---------------------------------------

### 899. MySQL Double Slash Delimiter `DELIMITER //`
```regex
^DELIMITER\s+\/\/\s*$
```
Detects lines that switch the delimiter to `//`.

---------------------------------------

### 900. JavaScript Private Field `#field` (ES Next)
```regex
\B#\w+
```
Captures references to a private class field.

---------------------------------------

### 901. IPv4 Ranges in Log Format: `10.0.0.0 - 10.0.0.255`
```regex
\d{1,3}(\.\d{1,3}){3}\s*-\s*\d{1,3}(\.\d{1,3}){3}
```
Find IP range lines.

---------------------------------------

### 902. Nim Procedure Definition: `proc name*(params: type) =`
```regex
^\s*proc\s+\w+\*\s*\([^)]*\)\s*=\s*$
```
Captures exported Nim procedures.

---------------------------------------

### 903. Ruby `if condition then ... end` on One Line
```regex
^\s*if\s+[^;]+then\s+[^;]+end\s*$
```
Compact form in Ruby.

---------------------------------------

### 904. `.gitattributes` Lines
```regex
^[^\s]+(\s+[^=]+=[^\s]+)*$
```
Rough match for patterns plus attributes.

---------------------------------------

### 905. `.NET` `DateTime.Parse("...")`
```regex
DateTime\.Parse\s*\(\s*(['"])[^'"]*\1
```
Matches calls like `DateTime.Parse("2025-03-12")`.

---------------------------------------

### 906. `tar` Extraction Command: `tar xvf archive.tar`
```regex
^tar\s+x[vzf]*\s+.+\.tar(\.[gx]?z2?|\.xz)?$
```
Captures `tar xvf`, `tar xvzf`, etc.

---------------------------------------

### 907. Comments in `.bash_aliases` Starting With `#`
```regex
^\s*#.*$
```
Simple detection of comment lines.

---------------------------------------

### 908. HTML `<td>` With `rowspan` And `colspan`
```regex
<td\b[^>]*\browspan\s*=\s*(['"])\d+\1[^>]*\bcolspan\s*=\s*(['"])\d+\2[^>]*>
```
Captures cells spanning multiple rows and columns.

---------------------------------------

### 909. `composer require vendor/package`
```regex
^composer\s+require\s+[a-z0-9_.\-]+\/[a-z0-9_.\-]+
```
Basic composer package install.

---------------------------------------

### 910. BFS/DFS Terms in Comments: `# BFS`, `# DFS`
```regex
^#\s+(?:BFS|DFS).*$
```
Captures lines referencing BFS or DFS in a comment.

---------------------------------------

### 911. Markdown Inline HTML `<p>text</p>`
```regex
<p>(.*?)<\/p>
```
Finds a simple paragraph tag usage in Markdown.

---------------------------------------

### 912. Four Dot-Separated Integers (Could Be a Loose Version)
```regex
^\d+\.\d+\.\d+\.\d+$
```
Captures something like `1.2.3.4`.

---------------------------------------

### 913. Jenkinsfile Declarative Pipeline `pipeline {`
```regex
^pipeline\s*\{\s*$
```
Captures the start of a Jenkins declarative pipeline block.

---------------------------------------

### 914. LaTeX `\label{...}` Commands
```regex
\\label\{[^}]+\}
```
Captures label references for cross-referencing.

---------------------------------------

### 915. JSON Keys in All Caps
```regex
"([A-Z0-9_]+)"\s*:
```
Find keys that are uppercase or underscores only.

---------------------------------------

### 916. Basic Microsoft Access Connection String
```regex
Provider=Microsoft\.ACE\.OLEDB\.\d+\.\d+;Data\s+Source=[^;]+;.* 
```
Captures typical Access provider connections.

---------------------------------------

### 917. Swift `lazy var name = ...`
```regex
^\s*lazy\s+var\s+[A-Za-z_]\w*\s*=\s*.*$
```
Lazy variable definition in Swift.

---------------------------------------

### 918. CSV Line With Mixed Quotes `'field1',"field2"`.
```regex
((['"][^'"]*['"])|[^,]+)(,|$)
```
Allows single or double quotes or unquoted segments.

---------------------------------------

### 919. Lines Containing a Single ASCII Word Surrounded by `""`
```regex
^"([A-Za-z]+)"$
```
No extra punctuation or spaces.

---------------------------------------

### 920. MySQL `SHOW TABLES;`
```regex
^\s*SHOW\s+TABLES\s*;\s*$
```
Captures that exact statement.

---------------------------------------

### 921. Docker `ARG` Instruction
```regex
^ARG\s+\w+=?.*$
```
Find `ARG NAME=VALUE` or `ARG NAME`.

---------------------------------------

### 922. Basic UPPERCASE_SNAKE_CASE With Digits
```regex
^[A-Z0-9]+(?:_[A-Z0-9]+)*$
```
Allows uppercase letters/numbers and underscores only.

---------------------------------------

### 923. Lines With `java -jar SomeApp.jar`
```regex
^\s*java\s+-jar\s+[^.]+\.jar\s*$
```
Captures usage of `java -jar`.

---------------------------------------

### 924. VSCode `launch.json` Configuration Keys
```regex
"configurations"\s*:\s*\[
```
Find the array of configurations in a `launch.json`.

---------------------------------------

### 925. A Domain Without Subdomain (Second-Level Domain Only)
```regex
^[A-Za-z0-9-]+\.[A-Za-z]{2,}$
```
No `sub.` allowed.

---------------------------------------

### 926. Jekyll Front Matter Separator: `---`
```regex
^---\s*$
```
Find lines that might denote start/end of front matter.

---------------------------------------

### 927. `helm install chart` Command
```regex
^helm\s+install\s+\S+\s+\S+
```
Captures `helm install` usage with a name and chart.

---------------------------------------

### 928. Lines That Contain a GitHub Issue/PR Reference: `#123`
```regex
#[1-9]\d*
```
Matches references like `#1`, `#12345`.

---------------------------------------

### 929. Basic Python `super()` Call: `super(ClassName, self)`
```regex
super\s*\(\s*\w+\s*,\s*self\s*\)
```
Identifies older Python2 style super usage.

---------------------------------------

### 930. Lines Ending With `&&` for Shell Command Continuation
```regex
&&\s*$
```
Captures lines that chain commands with `&&`.

---------------------------------------

### 931. A Basic Greek Letter in a Word: `\alpha`, `\beta` in TeX
```regex
\\(alpha|beta|gamma|delta|epsilon)
```
Common Greek letter TeX commands.

---------------------------------------

### 932. Pascal `writeln('Text');`
```regex
^\s*writeln\s*\(\s*'.*'\s*\);\s*$
```
Captures simple Pascal output lines.

---------------------------------------

### 933. IRB/Interactive Ruby Prompt Lines: `irb(main):001:0>`
```regex
^irb\(main\):\d{3}:\d+>
```
Identifies IRB prompt lines.

---------------------------------------

### 934. Windows Shortcut for a UNC Path `.lnk` With `\\Server\Share`
```regex
^[^\\/:*?"<>|]+\.(lnk)\s*\[\\\\[^\]]+\]$
```
(An invented pattern referencing path in brackets—example usage.)

---------------------------------------

### 935. Python `logging` Levels in Code: `logging.DEBUG`
```regex
logging\.(DEBUG|INFO|WARNING|ERROR|CRITICAL)
```
Find references to standard logging levels.

---------------------------------------

### 936. Basic WGET Command
```regex
^\s*wget\s+https?:\/\/\S+
```
Captures usage of `wget http://...`.

---------------------------------------

### 937. iOS/Objective-C Synthesize: `@synthesize property = _property;`
```regex
^\s*@synthesize\s+\w+\s*=\s*_\w+\s*;\s*$
```
Find lines that explicitly synthesize a property.

---------------------------------------

### 938. Strings Containing an Emoji in U+1F300–U+1F5FF Range
```regex
[\u1F300-\u1F5FF]
```
Matches one or more pictographic symbols (weather, emoticons, etc.).

---------------------------------------

### 939. JSON Pair With an Empty Object: `"key": {}`
```regex
"([^"]+)"\s*:\s*\{\s*\}
```
Finds keys mapped to an empty object.

---------------------------------------

### 940. Lines With `git push --force`
```regex
^\s*git\s+push\s+--force
```
Potentially overwriting remote commits.

---------------------------------------

### 941. MERN Stack `.env` Variables (Key=Value)
```regex
^[A-Za-z_][A-Za-z0-9_]*=.*$
```
Node environment variable pattern.

---------------------------------------

### 942. `.java` File With CamelCase Name
```regex
^[A-Z][A-Za-z0-9]+\.java$
```
Class-like filenames in Java.

---------------------------------------

### 943. Detect Lines With Windows Path `C:\folder\file`
```regex
^[A-Za-z]:\\[^<>:"/\\|?*]+
```
Captures Windows paths at start of line.

---------------------------------------

### 944. Indented JSON (One or More Tabs + Double Quotes)
```regex
^\t+"[^"]+":\s*
```
Key in JSON preceded by at least one tab.

---------------------------------------

### 945. Repeated Character at Start of Line
```regex
^(.)(\1)+
```
Captures if a line begins with at least two of the same char.

---------------------------------------

### 946. Spring Boot `@Bean` Annotation
```regex
^@\s*Bean\s*$
```
Identify lines defining a Spring bean.

---------------------------------------

### 947. A Single Lowercase Word With Non-ASCII Accents
```regex
^[a-z\u00C0-\u024F]+$
```
Matches extended Latin forms.

---------------------------------------

### 948. Distinguish “func.1.2.3” Possibly Versioned
```regex
^\w+\.\d+(\.\d+)*$
```
Find a name plus numeric dotted versions.

---------------------------------------

### 949. JavaScript ES6 Destructuring `const {a, b} = obj;`
```regex
^\s*const\s*\{\s*[A-Za-z0-9_,\s]+\}\s*=\s*\S+;
```
Captures destructuring assignment.

---------------------------------------

### 950. Locates `<cfset varName = "value">` in ColdFusion
```regex
<cfset\s+\w+\s*=\s*(['"]).*?\1\s*>
```
Captures CFML variable assignments.

---------------------------------------

### 951. Basic Svelte `bind:property={var}`
```regex
bind:\w+\s*=\s*\{\s*\w+\s*\}
```
Captures a Svelte binding.

---------------------------------------

### 952. Nginx `listen 80;`
```regex
^\s*listen\s+\d+\s*;\s*$
```
Find lines specifying the listen port.

---------------------------------------

### 953. XML `<tag attr="value"/>` Self-Closing
```regex
<([A-Za-z][A-Za-z0-9]*)(\s+[A-Za-z0-9:_-]+\s*=\s*(['"]).*?\3)*\s*/>
```
Captures self-closing tags with attributes.

---------------------------------------

### 954. Docker `RUN apt-get update && apt-get install`
```regex
^RUN\s+apt-get\s+update\s+&&\s+apt-get\s+install
```
Common Docker pattern.

---------------------------------------

### 955. Slack Channel With `#channel` in a sentence
```regex
(#\S+)
```
Find references to Slack channels in text.

---------------------------------------

### 956. Swift `guard let var = optional else { ... }`
```regex
^\s*guard\s+let\s+\w+\s*=\s*\w+\s+else\s*\{\s*$
```
Captures the start of a guard statement.

---------------------------------------

### 957. Email Address With Specific Allowed Characters (No plus)
```regex
^[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$
```
Doesn’t allow `+`.

---------------------------------------

### 958. TypeScript `interface` With Generics: `interface Name<T> { ... }`
```regex
^\s*interface\s+\w+\s*<[^>]+>\s*\{\s*$
```
Generic interface definition.

---------------------------------------

### 959. YAML Folded Block `>` With Indentation
```regex
^>\s*(\+|\-)?$
```
Catches `>` plus optional modifiers.

---------------------------------------

### 960. Slack usergroup mention: `<!subteam^S12345678|@group>`
```regex
<\!subteam\^[A-Z0-9]+(?:\|[^>]+)?>
```
Captures Slack usergroup mention.

---------------------------------------

### 961. HTML Tag That Ends Immediately `><` (No space)
```regex
><
```
Find places where tags butt up `><` without space or newline.

---------------------------------------

### 962. Extract ASCII Control Sequences `\x1B[...m`
```regex
\x1B\[[0-9;]*m
```
Captures SGR color codes (escape sequences).

---------------------------------------

### 963. Lines That Contain `chmod +x filename`
```regex
^\s*chmod\s+\+x\s+\S+
```
Shell command to make a file executable.

---------------------------------------

### 964. Python f-string Expression with Colon Format: `{var:.3f}`
```regex
\{[A-Za-z_]\w*:\.[0-9]+[a-zA-Z]\}
```
Extracts format specifiers inside f-strings.

---------------------------------------

### 965. Bower `bower install` Command
```regex
^\s*bower\s+install\s+\S+
```
Captures usage of Bower.

---------------------------------------

### 966. Inline C++ Comment `/*...*/` With No Newlines
```regex
\/\*[^*\n]*\*\/
```
Only single-line or no line break inside.

---------------------------------------

### 967. Grunt Task Runner: `grunt taskName`
```regex
^\s*grunt\s+\w+
```
Captures lines executing a Grunt task.

---------------------------------------

### 968. Liquid `{{ variable | filter }}`
```regex
\{\{\s*[A-Za-z_]\w*\s*\|\s*\w+\s*\}\}
```
Captures a variable with a single filter.

---------------------------------------

### 969. `.mjs` or `.cjs` File Extensions
```regex
^.+\.(?:mjs|cjs)$
```
Identifies ES module or CommonJS module files.

---------------------------------------

### 970. `pip list --outdated` Output Lines
```regex
^[A-Za-z0-9._-]+\s+[0-9.]+\s+[0-9.]+\s+.+$
```
Roughly matches 4+ columns typical of `pip list --outdated`.

---------------------------------------

### 971. JSDoc `@returns {Type}` Tag
```regex
^\s*\*\s*@returns?\s*\{\w+\}
```
Captures the return type annotation.

---------------------------------------

### 972. Puppet `file { 'title': ensure => ... }`
```regex
^file\s*\{\s*(['"])[^'"]+\1\s*:\s*ensure\s*=>\s*.+\}
```
Find a puppet `file` resource.

---------------------------------------

### 973. Apache Directory Block `<Directory "/var/www">`
```regex
<Directory\s+(['"])(.*?)\1>
```
Captures directory paths in quotes.

---------------------------------------

### 974. IPv6 Link-Local Address `fe80::` followed by something
```regex
^fe80::[A-Fa-f0-9:]+$
```
Basic link-local pattern.

---------------------------------------

### 975. CMake `target_link_libraries(target library)`
```regex
^\s*target_link_libraries\s*\(\s*\w+\s+\w+\s*\)
```
Captures minimal usage.

---------------------------------------

### 976. NodeJS Shebang `#!/usr/bin/env node`
```regex
^#!\/usr\/bin\/env\s+node\s*$
```
Typical Node shebang line.

---------------------------------------

### 977. `.ssh/authorized_keys` Key Type (e.g., `ssh-rsa`)
```regex
^(ssh-rsa|ssh-dss|ecdsa-sha2-nistp\d+|ssh-ed25519)\s+
```
Find lines with recognized key prefixes.

---------------------------------------

### 978. Simple BNF Rule: `identifier := <expression>`
```regex
^\s*\w+\s*:=\s*.*$
```
Captures a BNF-like grammar rule.

---------------------------------------

### 979. JavaScript `import { namedExport } from 'module';`
```regex
import\s*\{\s*[\w,\s]+\}\s*from\s*(['"])[^'"]+\1
```
Captures a named export import statement.

---------------------------------------

### 980. HTML With `lang="en"` in the `<html>` Tag
```regex
<html\b[^>]*\blang\s*=\s*(['"])en\1[^>]*>
```
Finds the `<html lang="en">` attribute.

---------------------------------------

### 981. Basic Debian `apt-key` Commands
```regex
^\s*apt-key\s+(add|del|list|finger)
```
Captures usage of apt-key subcommands.

---------------------------------------

### 982. Lines With GPG Trust Model `trust-model always`
```regex
^\s*trust-model\s+always\s*$
```
Possible config line in GPG/gpg.conf.

---------------------------------------

### 983. Docker Compose `service:` Port Mapping `ports: ["80:80"]`
```regex
^\s*ports:\s*\[\s*(['"])\d+:\d+\1\s*\]
```
Captures a simple port mapping array in a YAML line.

---------------------------------------

### 984. Ruby `%Q{} String`
```regex
%Q\{[^}]*\}
```
Match a `%Q{...}` quoted string in Ruby.

---------------------------------------

### 985. Tomcat `<Context>` Tag
```regex
<Context\b[^>]*>
```
Captures a `<Context>` configuration in Tomcat server.xml or context.xml.

---------------------------------------

### 986. Checking for Lines With Only `}` or `);`
```regex
^(?:\}|\);\s*)$
```
Simple bracket or parenthesis close.

---------------------------------------

### 987. C++ `#pragma once`
```regex
^#\s*pragma\s+once\s*$
```
Matches single-include guard directive.

---------------------------------------

### 988. Java `public static void main(String... args)`
```regex
^\s*public\s+static\s+void\s+main\s*\(\s*String(\.\.\.)?\s+\w+\)\s*\{$
```
Variant with varargs.

---------------------------------------

### 989. SystemD `[Unit]` Section
```regex
^\[Unit\]\s*$
```
Captures the start of `[Unit]` in service files.

---------------------------------------

### 990. JSON Lines That Are Just an Empty Array: `[]`
```regex
^\[\s*\]$
```
No elements inside.

---------------------------------------

### 991. HTML `form` Without a `method` Attribute
```regex
<form\b(?![^>]*\bmethod\b)[^>]*>
```
Checks if `method=` is missing.

---------------------------------------

### 992. `StringIO` usage in Python
```regex
StringIO\(\s*(['"]?).*\1\s*\)
```
Captures `StringIO("text")` usage.

---------------------------------------

### 993. `keytool -genkey` Command
```regex
^keytool\s+-genkey\b
```
Find Java keytool command for generating keys.

---------------------------------------

### 994. `.NET` property in a `.resx` file: `<data name="...">`
```regex
<data\s+name\s*=\s*(['"])[^'"]+\1
```
Captures resource data definitions.

---------------------------------------

### 995. `pytest` marker: `@pytest.mark.something`
```regex
^@\s*pytest\.mark\.\w+
```
Simple test marker usage in Python.

---------------------------------------

### 996. Memcached `set key 0 900 9`
```regex
^set\s+\S+\s+\d+\s+\d+\s+\d+$
```
Captures basic memcached `set` command line.

---------------------------------------

### 997. Xcode `.xcworkspace` or `.xcodeproj`
```regex
^.+\.(?:xcworkspace|xcodeproj)$
```
Matches either extension for Xcode.

---------------------------------------

### 998. YAML Sequence of Maps: `- key: value`
```regex
^-\s+\w+\s*:\s*.*$
```
Catches `- name: John`.

---------------------------------------

### 999. Single Quoted Strings That Allow Escaped Single Quote `\'` Inside
```regex
'(?:\\'|[^'])*'
```
Permits `\'` within single quotes.

---------------------------------------

### 1000. K8s YAML Resource Kind: `kind: Deployment`
```regex
^\s*kind\s*:\s*\w+$
```
Captures lines specifying a Kubernetes resource kind.

---------------------------------------
