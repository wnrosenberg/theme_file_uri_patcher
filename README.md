# theme_file_uri_patcher #
## &ldquo;18302 was a pretty cool ticket.&rdquo; ##

Of course I'm referring to https://core.trac.wordpress.org/ticket/18302 which introduces some brilliant functionality into the whole child themeing process.

You pass a filename and it first checks whether it exists under get\_stylesheet\_directory\_uri(). If it doesn't exist, it returns the filename under get\_template\_directory\_uri(). You get back either the overriding file uri from the child theme, or a file uri from the parent theme.

This is useful because reasons. See the ticket. 

## What does this plugin do? ##

*Adds Methods!* It adds theme\_file\_uri() and parent\_theme\_file\_uri() [_as of 18302.14.diff_].

*Does Patching!* With a click of a button it will replace get\_stylesheet\_directory\_uri() (followed by the $filename, which is detected by regex) with theme\_file\_uri($filename), and replace get\_template\_directory\_uri() + $filename with parent\_theme\_file\_uri($filename).

*Maeks Backups!* Pre-patch versions of template files affected by the patch will be stored as $filename.'.prepatch.'.$extension.'.bak';

*Hey! Listen!* Listens for when the parent theme gets updated and then prompts you to re-run the patcher to help prevent your child theme from breaking.

## Neato. When do you think you'll actually code it out? ##

_Ummmm....._ IDK.
