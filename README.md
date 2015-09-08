# smart-bbcode-parser
A smart PHP based unicode compliant bbcode parser that doesn't use regular expression...

[Synopsis]

Smart BBCode Parser aims to offer an alternative to the the other resource intense BBCode parsers that you will most undoubtedly
find on the interweb today. Instead of just trying to get something done, the Smart BBCode Pasrer is being designed to show others why
'Reinventing Wheel' is sometimes the only way to fix the problems that exist in every other BBCode Parser that I have examined....

[Code Example]

Loading.... (smart_bbcode_parser)

<?php

require_once ( '/objects/spl.php' );

spl::autoloader();

/* initiate the smart_bbcode_parser */

$parser = new smart_bbcode_parser ();

/* load the default bbcode(s) from a file */

$parser->load_default_bbcodes ( 'file' );

/* add unicode support to the parser */

$parser->make_parser_unicode_aware ();

/* parse a text string with the parser */

$string = '[b]bold[/b]
[i]italic[/i]
[u]underline[/u]
[s]strike[/s]

[color=red]red text[/color]
[size=3.0em]the size of this text is 3em[/size]
Hi [font=\'"comic sans ms", watermelon, times, sans-serif\'][b][b][b][g]Sonia[/g][/b][/b][/b][/font]!
';

$string = $parser->parse_bbcode_string ();

Return(s)....

[code]

/*
*
* Notice it doesn't just parse bbcode, it also cleans ups the html and removes redundant and bogus bbcodes and, or their bogus values
*
* <span style='font-weight: bold;'>bold</span>
* <span style='font-style: italic;'>italic</span>
* <span style='text-decoration: underline;'>underline</span>
* <span style='text-decoration: line-through;'>strike</span>
*
* <span style='color: #FF0000;'>red text</span>
* <span style='font-size: 3em;'>the size of this text is 3em</span>
* Hi <span style='font-family: "comic sans ms", times, sans-serif; font-weight: bold;'>Sonia</span>!
*
*/

?>
[/code]

[Contributors]
Sonia Desbiens, John Ricci

[API Reference]

links to the API, will be added within the next month....

[Some Of The Parsers Methods]


/* initiate the smart_bbcode_parser */

$parser = new smart_bbcode_parser ();

/* load the Smart BBCode Admin Panel */

<?php

$admin = new smart_bbcode_admin ();

$admin->bbcode_admin_panel ();

?>

loads a powerful admin panel that allows one to manage their bbcodes, configuration options, the admin panel can also build a smart_bbcode_parser that only includes the properties and methods you need to plugin into whatever application you want to add the parser too. 

configuration options

manage bbcodes (set removal / combining rules / set validation routines, change replacement templates)
bbcode storage (file/db)
default configuration options...
turn a bbcode on / off
add / delete bbcodes

back to the parser....

/* return an information array of all bbcode tags found in a string */

$array = $parser->return_bbcode_array ( $string );

/* return a tree view of all bbcode tags found in a string */

$tree = $parser->return_bbcode_tree ( $string );

/* return a bbcode string from a html string  */

$bbcode = $parser->return_bbcode_array ( $html );

/* fetch a web page and convert it into a bbcode string */

$bbcode = $parser->return_bbcode_webpage ( 'http://www.google.com/' );

...



The MIT License (MIT)

Copyright (c) 2015, Sonia Desbiens, John Ricci

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
