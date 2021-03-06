


# About Urtext



## Description 

Urtext is a syntax and interpreter for plaintext. Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A folder of nodes is a "project". The Urtext interpreter is aware of all the nodes in a project at once, so nodes can reference, modify, and organize one another, across hundreds or thousands of files. The [Basic Syntax](#basic-syntax) permits instructions embedded into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python 3.3 or later runs. Equivalent or variant interpreters could be created in any language or editing environment. 

Urtext has no built-in user interface; it only compiles and manages the files. Using Urtext in a text editor requires an additional wrapper to pass messages between the text editor and Urtext. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).  



## Comparison To Other Tools 

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. Though it can export, Urtext is not primarily a document conversion or document generation tool. It is rather a tool for writing, connecting and organizing text.

Urtext consolidates content, structure and instructions (scripting) into a single compilable syntax. Although it can link documents or parts of documents together, unlike HTML, there is no additional code or markup "behind" the visible syntax. Everything the interpreter reads is visible to the user.



## Uses  

- prose writing
- research
- documentation
- knowledge/information base
- journaling
- Zettelkasten
- project/personal organization
- notetaking
- lightweight database
- any other writing or information management that can be done in text form




## Features and Philosophy  

- It uses plain text files. Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof.

- It can compile, organize, and link content spread across hundreds or thousands of files. Files and content elements can be linked to one another in tree-like, recursive (tangled), and other non-hierarchical ways.

- Cascading complexity; use only the parts you need. Does not take months/years to learn.

- It is usable across multiple platforms and devices.

- Being open source, Urtext is extensible, hackable and customizable to specific needs.

- It has customizable and extensible metadata that does not rely on the file system.

- It is decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

- It can incorporate (embed) other plaintext syntaxes, including other markup languages and other programming language syntaxes.

- There is no need to interact directly with the file system (creating, naming, saving, organizing files). File creation, naming and management is handled for you.

- Future-proof. No reliance on anything that may not exist in 5 or 1000 years. Urtext files themselves are in plaintext, which is future-proof. The interpreter/compiler could be implemented in any sufficiently capable language desired, current, past or future.

- Does not depend on a cloud service. Though cloud services can be used to sync project files among devices, the interpreter itself is made to operate locally; content wholly resides on the device being used.

Being in plaintext and having a syntax specification, it can also be used with:

- Themes and syntax highlighting.

- Version control (Git, for example).   




# About This Documentation 

This is a documentation of Urtext, written in Urtext. The `README.MD` on it was exported from the text files in this repository. Clone or download the respository to use it as both reference and example project. 

This documentation is in active development. It may be incomplete or behind features/functionality of Urtext. Edits and revisions are encouraged in the form of issues and pull requests (>https://github.com/nbeversl/urtext-docs/pulls, https://github.com/nbeversl/urtext-docs/issues).

Many of the examples rely on syntax and formatting that are stripped out in export to Markdown. These are replaced with screenshots as necessary (see [Linking to Files and Other Resources](#linking-to-files-and-other-resources) and [Exporting](#exporting))

Inside an Urtext implementation, such as the Sublime Text with the Urtext package, you can navigate the project directly. Most of the key commands utilize Control-Shift as the modifier. 
- Control-Shift-/ to follow any link
- Control-Shift-h at any time to return to this "home" node. 
- View the readme: [readme.md ; ](readme.md ; )


# Quick Start, Guides and Examples  



## Installation and Setup (Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at `https://github.com/nbeversl/urtext_deps`. You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use `git clone --recurse-submodules https://github.com/nbeversl/urtext_deps`. Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.

3. Download the Sublime Urtext package at `https://github.com/nbeversl/urtext_sublime`. Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select `Urtext : Initialize Project` from the Sublime Command Palette. For more information, see [Projects](#projects).

See also:

[Sublime Text Interface Tips](#sublime-text-interface-tips)



## Basic Syntax


All text is plain content unless inside a timestamp wrapper, dynamic definition wrapper, or preceded by a metadata assignment operator and keyname.

`{  }`
Inline Node Wrappers. Can appear anywhere. Can be nested aribrarily deep.
More information: [Inline Nodes](#inline-nodes)

`>`
Node Link. Links to the specified node by ID, like a hyperlink. 
More information: [Links](#links)

`>>`		
Node Pointer: Embeds the specified node as though it were included inline using wrappers `{ }` (see above)
More information: [Pointers](#pointers)

`|`
Title Pipe. Placed immediately before a node link or node pointer (whitespace is ok), dynamically populates the linked node title.
Example and more info: [Dynamic Titles](#dynamic-titles)

`•`
Compact Node marker. Must be the first non-whitespace character on a line. Must include an ID in order to parse.
More information: [Compact Nodes](#compact-nodes)

`< >`
Timestamp wrapper. Parses user-defined datetime strings, with many default formats built in.
The first character inside the brackets may not be `!`, '-', or whitespace.
Example: 
More information: [Syntax and Format](#syntax-and-format)

`::`
Metadata assignment operator. Accepts a user-defined key on the left, and values and timestamps on the right.
Metadata may appear anywhere. They attach to their containing (parent) node, remember their exact location, and can serve as anchors/bookmarks to context. Keys must be single words (underscore permitted), values may be any characters, terminated with a semicolon or newline. The pipe character (`|`) separates multiple values for a single key.
Example: 

More information: [Metadata](#metadata)




## Dynamic Definitions : Syntax and Parameters

Dynamic definitions are instructions for dynamically building nodes from other nodes. Definitions can be written anywhere; it is not necessary to store the definition in the same file to which it refers. (Note that they cannot, however, be stored in the node they target, since they would overwrite themselves.)

Dynamic definitions are wrapped with double left and right square brackets(``). There are no restrictions on spacing, indentation, newlines, or other arbitrary text or whitespace. Dynamic definitions ignore whitespace and arbitrary text outside other than defined parameters. The order of parameters within a definition is unimportant; they are evaluated as a group.

The dynamic definition is for documentation and does not actually do anything. It rather lists every parameter along with an explanation of its use and purpose. For example uses, see [Dynamic Nodes](#dynamic-nodes)


[[ 	ID() 			Target node to dynamically populate with output.
Accepts a link to a node [ MISSING LINK : eee ] )

INCLUDE()  		Nodes to include. Accepts one or more key/value pairs and optional parameters.
or +()
Comparisons:

`=` means equal to
INCLUDE(key = value)	
Includes all nodes with the given key containing the given value

`?` means "contains"
INCLUDE(_contents ? some text or content)
Includes all nodes containing "some text or content" in their text contents.
(See also -search)

`*` means "anything"
INCLUDE(index = *)
Includes all nodes containing the key `index`

Use semicolon or newline to separate entries, as everywhere in Urtext.

Additional Flags:

Additional flags can be included in 

INCLUDE(*) or +(*)
Includes all nodes in the project									

`-all_projects` or `*p`
INCLUDE(-all_projects) or +(*p)
Expands included nodes to include all projects in the project list.

`-blank`
Includes all nodes that contain only whitespace as their content

Note these additional flags substitute for semicolons/newlines as separators between entries.

System keys

Urtext includes some built-in keys whose values are generated automatically. 
These may also be used in INCLUDE(): 

`_links_to`			
INCLUDE(_links_to = 46d)
Includes all nodes that contain links to node ID `46d`

`_links_from`
INCLUDE(_links_from = 46d)
Includes all nodes to which node ID `46d` links

`_contents` : Refers to a node's text contents. 
Can be used, for instance, for full text search or comparison.
INCLUDE(_contents ? Western Civilization)
Includes any node that contents the text "Western Civilization"
(comparisons are case-insensitive)

EXCLUDE()		Accepts all the same parameters as INCLUDE()
or -()			Always evaluated after INCLUDE(), excludes the specified nodes from the result.



SORT()			Sorts the results. Entries can be keynames (include system-defined ones, see below)
or flags, with multiple keys separated by semicolon or newline.

SORT(

[ key name ]		Sorts by the value of the given key. Default is alphabetical.

-num or -n  		Sorts the results numerically if possible.
The default sort is alphabetical.

-timestamp or -t  	Sort by timestamp

-reverse or -r 		Reverses the sort order. Applicable to any of the above.

)

Note that system-assigned keys are also available:

`_last_accesssed`
`_contents`

Example:
SORT(title -reverse)

LIMIT()			Limits the output to the specified number of results.
Limit is applied after SORT().

Example:
LIMIT(30)
Will only show 30 results of nodes with the specified INCLUDE()/EXCLUDE() parameters.


DEPTH()			By default, the dynamic output will be a list of (unique) nodes specified by the
combination of INCLUDE() with EXCLUDE(). To see instead a tree representation of each node and its 
descendants, if any, provide a levels of depth. Example: DEPTH(5).

To see infinite levels (until recursion occurs) use DEPTH(*). 

COLLECT()		Aggregates occurrences of metadata, including timestamps, and surrounding contents.
Accepts key/value pais 
Returns a seperate item for each occurence.

Example:
COLLECT(timestamp=*)


SHOW()			Supplies a template for the output of each result. 
Accepts keynames, denoted with `$`, arbitrary text, and Unicode characters including \n, \r, \t.

Words preceded by `$` are are evaluated as metadata keys, replaced in the output by their value(s).
Note that key names themselves are not displayed in the output. Add keynames manually if you want them included.

Example:
SHOW(Author: $author, Date: $date\n)

In addition to all user-defined metadata keys, the following tokens are included:

SHOW(

$title 
Displays the node title, default or via the `title` meta key

$link
Displays a link to the node

$date 
Displays the node's date in the project's default timestamp format

$meta
Shorthand to show all metadata for every node, formatted as by "consolidate metadata"

$contents:120
Displays the contents of the node. Optional excerpt/length specifier after the colon
)

HEADER()		Adds additional arbitrary/freeform text to the beginning of the output. This can include any syntax 
valid inside Urtext nodes, including metadata.

FOOTER()		Adds additional arbitrary/freeform text to the end of the output. Same as for HEADER().

EXPORT()		Exports the output to a Plaintext, Markdown, or HTML, into another node or into an external file.
Accepts one or more semicolon- or newline-separated links to nodes or files (see | Linking to outside 
resources[Linking to Files and Other Resources](#linking-to-files-and-other-resources)), such as: 


To include all nodes pointed to from the root file, recursively, use the flag:
-rr or -recursive

It also accepts one of the following flags to specify the output:

-plaintext or -txt	

This is the default.
Strips all Urtext syntax, including metadata and dynamic definitions.
Can be used, for instance, to export a node or nodes to a non-Urtext text file.

-markdown or -md	

Outputs a Markdown representaion of the node(s).
Will include all hierarchically nested nodes using Markdown heading format.
See FORMAT() for ways to preformat the output.

-html

Outputs HTML

FORMAT()		Specificies additional global formatting of the output. There are intended primarily for formatting 
exported text, but can be applied to any output. Accepts one or more predefined flags:

-preformat or -pre
Wraps preformatted text (trees, etc.) in backticks to preserve preformatting, 
for instance, for Markdown contenxts.

-multiline_meta or -mm
Places dynamic node metadata on separate lines instead of separated by;

-indent: or -i
Indents the dynamic node by the number of spaces specified in parentheses.
Example: FORMAT(-indent:20)

]]  




## Key Bindings and Operations



### Navigation 


#### Node Browser, Backlinks: `ctrl + shift + 1`     	@1ea


#### Nav Backward: `ctrl + shift + ,`   				@3hy


#### Home Node: `ctrl + shift + h`  					@5ab


#### List Projects: `ctrl + shift + o`  				@g5a


#### Toggle Traverse Mode: `ctrl + shift + r`   		@hcf


#### Node Browser, Include All Projects: `ctrl + shift + *`  @hyh


#### Open Urtext Link:	`ctrl + shift + /` 				@ngh


#### Open Random Node: `ctrl + shift + f`  				@q5f


#### Node Browser: `ctrl + shift + e`   				@vdr


#### Nav Forward: `ctrl + shift + .` 					@yan


#### Node Browser, Forward Links: `ctrl + shift + 2`   	@ylo
@k7b 



### Content Insertion 


#### Insert Compact Node: `ctrl + shift + ^`   		@1qq


#### Insert Timestamp: `ctrl + shift + t`    			@7b8


#### Insert Inline Node, minimal: `ctrl + shift + p` (OSX), `alt  + shift + p` (Windows, Linux)  @6ym


#### Add Node ID: `ctrl + shift + i`  				@gv9


#### Insert Dynamic Definition with Node: `ctrl + shift + ` Insert Dynamic Definition with Node: `ctrl + shift + }`	@jsc


#### Insert Inline Node: `ctrl + shift + ` Insert Inline Node: `ctrl + shift + {` 			@rzx


#### Insert Link to New Node: `ctrl + shift + '` 		@sxk


#### New Node: `ctrl + shift + ;`  					@ve3


#### Quick Tag from Other: `ctrl + shift + 0` 		@zep
@kxh  



### Copy Links 


#### Copy Link to this Node With Title: `ctrl + shift + super + c`  	@05x


#### Copy Link to this Node: `ctrl + shift + c`  	@vel
@kqz  



### History 


#### Toggle History Traverse: `ctrl + shift + g`  @ndc
@a8q 





## Sublime Text Interface Tips

Here are some tips for best leveraging Sublime's great UI features while using Urtext.



### Syntax Highlighting 

The Sublime Text package includes a syntax definition file in YML format (`sublime_urtext.sublime_syntax`), along with two color schemes that provide syntax highlighting. Syntax highlighting makes everything easier by showing depth of node nesting and dimming certain elements of the syntax. Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ... 

Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (This can be undone by repeating the same but selecting Plain Text.) 



### Hiding Tabs	

If you prefer a spare, terminal-like view, hide tabs: View -> Hide Tabs.
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation. 



### Hiding Line Numbers  

For an extra-clean look, hide line numbers by adding:

```

"settings" : {
"line_numbers": false,
},

```

... to your Sublime project settings file. 

(Ignore the JSON syntax pass markers above beginning with `%%`. See [Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers) )



### Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode. 



### Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
```
"settings" : {
"always_prompt_for_file_reload": false,
},
```		





### Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:

```
"settings" : { 
"draw_indent _guides": false,
}
```




### Save on Focus Lost  

Urtext recompiles your project every time a file changes. To make this more automatic, and to reduce the need to manually press save after every edit, add to your Sublime settings file:

```
"settings" : { 
"save_on_focus_lost": true 
}
```





### Using a Sublime Project for an Urtext Project  

( see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.  








# Reference   


## About Urtext



### Description 

Urtext is a syntax and interpreter for plaintext. Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A folder of nodes is a "project". The Urtext interpreter is aware of all the nodes in a project at once, so nodes can reference, modify, and organize one another, across hundreds or thousands of files. The [Basic Syntax](#basic-syntax) permits instructions embedded into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python 3.3 or later runs. Equivalent or variant interpreters could be created in any language or editing environment. 

Urtext has no built-in user interface; it only compiles and manages the files. Using Urtext in a text editor requires an additional wrapper to pass messages between the text editor and Urtext. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).  



### Comparison To Other Tools 

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. Though it can export, Urtext is not primarily a document conversion or document generation tool. It is rather a tool for writing, connecting and organizing text.

Urtext consolidates content, structure and instructions (scripting) into a single compilable syntax. Although it can link documents or parts of documents together, unlike HTML, there is no additional code or markup "behind" the visible syntax. Everything the interpreter reads is visible to the user.



### Uses  

- prose writing
- research
- documentation
- knowledge/information base
- journaling
- Zettelkasten
- project/personal organization
- notetaking
- lightweight database
- any other writing or information management that can be done in text form




### Features and Philosophy  

- It uses plain text files. Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof.

- It can compile, organize, and link content spread across hundreds or thousands of files. Files and content elements can be linked to one another in tree-like, recursive (tangled), and other non-hierarchical ways.

- Cascading complexity; use only the parts you need. Does not take months/years to learn.

- It is usable across multiple platforms and devices.

- Being open source, Urtext is extensible, hackable and customizable to specific needs.

- It has customizable and extensible metadata that does not rely on the file system.

- It is decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

- It can incorporate (embed) other plaintext syntaxes, including other markup languages and other programming language syntaxes.

- There is no need to interact directly with the file system (creating, naming, saving, organizing files). File creation, naming and management is handled for you.

- Future-proof. No reliance on anything that may not exist in 5 or 1000 years. Urtext files themselves are in plaintext, which is future-proof. The interpreter/compiler could be implemented in any sufficiently capable language desired, current, past or future.

- Does not depend on a cloud service. Though cloud services can be used to sync project files among devices, the interpreter itself is made to operate locally; content wholly resides on the device being used.

Being in plaintext and having a syntax specification, it can also be used with:

- Themes and syntax highlighting.

- Version control (Git, for example).   




## Projects

An Urtext project is a single folder. The folder must contain at least file with an Urtext Node ID.

To make an new empty project:

- make a new folder and open the folder in Sublime Text. 
- Select Urtext : Initialize Project from the Sublime Command Palette. 
- The folder how has one Urtext file and a `history` folder for tracking edits. (See [History](#history) )



### Using/Adding Existing Files 

Once a folder contains at least one file with a node ID, you can add and use existing plaintext files in the project without any modification. However for most of the benefits of Urtext you must minimally an ID ([Node IDs](#node-ids)) in each file.

To do so, select `Urtext : Import Project` from the Sublime Command palette.

Note the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.



## Nodes

A node is region, or set of regions, of a file, up to and including the entire file. A file is itself a node. All nodes can contain other nodes.

The identity of an Urtext node persists no matter its containing filename. This is accomplished by assigning each unique identifier, providing over 46,000 possible nodes per project. See [Node IDs](#node-ids) for more information.

Urtext generates IDs automatically on creation of new nodes. ID's can be changed without affecting functionality, though links must then be manually updated as well. 

It is possible to use files containing no IDs in an Urtext project, but then most of the features of Urtext are lost.



### Types of Nodes  


#### File Nodes

The most basic node is a single file. It may or may not contain other nodes nested inside it.

To create a new file-level node: [New Node: `ctrl + shift + ;`](#new-node:-`ctrl-+-shift-+-;`). A new file is created, named and saved automatically. It has whitespace on top and a metadata block at the bottom containing a node ID and (by default) a creation timestamp.



#### Inline Nodes                                                       

Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another inline node. For all purposes in Urtext, inline nodes' identities are unique from their containing files, parent nodes, and child nodes.   

The syntax for inline nodes is to wrap the content in curly braces:



##### Example Inline Node   


Create an inline nodes with [Insert Inline Node: `ctrl + shift + `](#insert-inline-node:-`ctrl-+-shift-+-`). Inside the inserted double curly braces is a new node with an auto-generated ID.   

To wrap existing content into an inline node, first select the content and use the same keypress.

When syntax highlighting is active, inline node wrappers are tinted to showing nesting level:



(For Markdown export, a screenshot is provided showing indentation and highlighting:) [./files/node-nesting-example.png](./files/node-nesting-example.png)

Note that every opening curly bracket must be closed in the same file. Every node requires an ID between its opening and closing brackets. Nodes at the file level ([File Nodes](#file-nodes)) do not use curly-braces, as their region boundaries are the file itself.




##### Escaping Curly Brackets  

If you need to use curly brackets in your text, you can escape the Urtext syntax by preceding the bracket with a backward slash; this will prevent them from being parsed: \{ \}

To ignore syntax elements more globally, and/or to embed other syntaxes that use Urtext characters, such as JSON, PHP, and JavaScript, see [Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers)






#### Compact Nodes

Key: [Insert Compact Node: `ctrl + shift + ^`](#insert-compact-node:-`ctrl-+-shift-+-^`)

For text content requiring only a single line, such as list items, very short notes and similar, use the caret character (`^`) as the first non-whitesoace character on a new line. This defines a new node as a child of the node in which the character appears, with the closing wrapper being the end of the same line. 

Like all nodes, a compact node requires an ID. Like all nodes, it can contain metadata and even inline nodes, as long as the entire contents, including wrappers and metadata, are contained on a single line. (Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)




[./files/example-compact-node.png](./files/example-compact-node.png)

   



### Node Titles 

By default, the full first non-whitespace line of any node is the node's title. This can be overridden using the `title` metadata key or by following the desired text with the underscore (`_`) character as used in this document.



## Metadata



### General Syntax 

Every node can have an unlimited number of metadata entries. Metadata is structured in double-colon-separated key/value pairs, with the value (to the right of the colon) containing an optional timestamp. Examples:




Nodes can be searched and sorted by their metadata using [Dynamic Definitions](#dynamic-definitions). Metadata entries also "remember" their location, allowing them to serve double duty contextual markers or "bookmarks". 

Other than a few reserved key/value pairs, metadata is user-defined. Keys must be single words, though characters such as dash and underscore are allowed. Values may include spaces. Terminate metadata entries using either a new line or a semicolon. Using the semicolon option, several entries may be strung together on a single line:



Note that a timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexed.



### Timestamps                                                                  



#### Syntax and Format   

Text between two angled brackets (`< >`) is parsed as a timestamp whenever the first character inside the brackets is not `!`, `-` or whitespace. Urtext utilizes the Python `dateutil` module to loosely parse dates in almost any format. For instance, all of the following are valid:





... and so on

Press [Insert Timestamp: `ctrl + shift + t`](#insert-timestamp:-`ctrl-+-shift-+-t`) to insert the current date and time anywhere. The format of the resulting timestamp can be changed in project_settings using the [`timestamp_format`](#`timestamp_format`) key.

Timestamps may also be used anywhere without a keyname; "inline" timestamps that are not part of a keyed metadata entry are auto-assigned the keyname `inline-timestamp`. Like all metadata, they remember their position and may function doubly as anchors/bookmarks.



#### Tracking Node Dates and Times   

Reliance on the operating system's "created" or "modified" file date metadata is avoided, since these can be inadvertently overwritten during ordinary file system operations. Instead, new file-level nodes receive a "timestamp" metadata key by default when created: 



#### Time Zones   

Time zones are not required. If no time zone is present, Coordinated Universal Time (UTC) is added by default for parsing/comparison purposes. To modify this default, set the  [`timezone`](#`timezone`) key in project_settings to another valid value.





### Case-sensitivity  

For comparison/filtering/sorting purposes, values are not case-sensitive.



### Reserved Keys 

There are two reserved keys that Urtext interprets in a special way:



#### `index`   

Provides a way to give nodes a sort order in [The Node Browser](#the-node-browser).  Indexed nodes will sort before (above) the others, lowest numbers appearing first. To utilize, add a two-digit sort index (00-99) to a node, such as:  
You can give the same index number to multiple nodes; in this case they sort first by index, then by timestamp, newest first.

Unindexed nodes will display underneath indexed nodes, by timestamp, newest first.



#### `title` 

Overrides the node title, which is by default the full first non-whitespace line.



#### `def`  

Generated automatically in a dynamic node, contains a link to the node containing the definition.






## Dynamic Nodes

Dynamic nodes contain content aggregated from the contents of other nodes. Dynamic content stays up to date with its source content "dynamically" (on file save). A dynamic node can be seen as a "view into" other content. 



### Dynamic Definitions 

Dynamic nodes are created using a Dynamic Definition. Dynamic Definitions are specified with double square brackets , and have there own syntax, including scoping and highlighting. Dynamic definitions can query, sort, filter, and format the output of nodes in a variety of ways, making them adaptable to many purposes. This section illustrates some example uses of dynamic nodes. It will be helpful to reference [Dynamic Definitions : Syntax and Parameters](#dynamic-definitions-:-syntax-and-parameters).

Dynamic Definitions can be written anywhere; it is not necessary to store the definition in the same file to which it refers. (Note that they cannot, however, be stored in the node they target, since they would overwrite themselves.)

The key [Insert Dynamic Definition with Node: `ctrl + shift + `](#insert-dynamic-definition-with-node:-`ctrl-+-shift-+-`) creates a new dynamic definition in Sublime, auto-populated with a corresponding empty inline node. You can also write a definition manually, providing the ID of an existing node. For example, if you want the contents to replace an existing node, assign this key the value of that node's ID. If you want it to populate new inline node, create that node and then copy/paste its ID. Note that Dynamic Definitions do not create their target nodes automatically ; the target node must exist, or the definition will have no effect.  

There are two main kinds of dynamic output, Lists and Collections:

"Lists" are lists of nodes, with each node displayed not more than once. Lists can optionally expand into trees, showing the hierarchy of nested relationships from each root node in the list.



### Lists





[./files/example-list-1-definition.png](./files/example-list-1-definition.png)
[./files/example-list-1.png](./files/example-list-1.png)

Note that the at the bottom of the node is the reserved key `def` which refers to the node containing the definition.



Lists can be expanded into trees that show the outline of many nodes across many files at any specified depth, up to. In fact, a list is a tree with depth 1.



### Trees



#### Expanding a List with the DEPTH Parameter  







In practice most of these nodes have only a 2-3 levels of nesting. For an example of a larger tree, look at the 

#### "Table of Contents" Dynamic Definition

Here is the dynamic definition that generates the [Table of Contents](#table-of-contents) for this documentation.








[./files/toc-dynamic-definition.png](./files/toc-dynamic-definition.png)
[./files/excluded-from-toc-definition.png](./files/excluded-from-toc-definition.png)
[./files/excluded-from-toc-list.png](./files/excluded-from-toc-list.png)

See also the definition that dynamically creates the README.md version of this documentation:
[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file)


Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.



"Collections" aggregate metadata entries with their context; the same node may appear many times in a collection if it contains many metadata entries matching the queried parameters.



### Collections

Collections "collect" metadata entries. 

Metadata entries remember their position in their node and so can be used as anchors or "bookmarks". There are no "prescribed" uses for this functionality; metadata entries could be used in any given project as anchors only, metadata only, or in combination.

For instance, metadata could be used to insert 

Collections return links that include the exact character location of each metadata entry. This is 

Another use would be to collect all metadata entries of a given key, and optionally a given value, into a single view. 










## Links and Pointers



### Links   

To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.



#### Sublime Text tools to help with linking   


Two Sublime Command Palette commands can make linking quick and easy:

Urtext : Link To ...
Links from the currently viewed node to another node which you can select in the selection panel. When you select a node in the quick panel, a link to that node will be inserted at the cursor.

Urtext: Link From ...
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.




### Dynamic Titles  

Prepending a pipe character to any node link will populate the space between the pipe and link with the node's title, from its metadata or default title. Examples are found throughout this documentation. Titled links are updated at the single file level whenever the file is saved. 



### Opening Links  



#### Sublime 
Key : [Open Urtext Link:	`ctrl + shift + /`](#open-urtext-link:	`ctrl-+-shift-+-/`) on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point. 




#### Pythonista  

Use the `/` botton when the cursor is on any line containing a link.


Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save. 




### Linking to Files and Other Resources



#### Web / HTTP(S) 

HTTP(S) links are recognized automatically and will open in the default browser.    
Example: pressing [Open Urtext Link:	`ctrl + shift + /`](#open-urtext-link:	`ctrl-+-shift-+-/`) on this line will open the link: http://github.com




#### Files 

Links to files can be made by writing `f>`, followed immediately with a file path relative to the folder of the project:
Example: [README.md](README.md)




### Pointers          

By preceding a link to a node with two right angle brackets instead of one, you can extend trees beyond the file level to create node relationships spanning many files. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as descendants of the node containing the Pointer:



##### Example Child Node Using a Node Pointer
 

The example Pointer above becomes a child of this node, visible in the [Table of Contents](#table-of-contents) or using the other tree views described in [Trees](#trees).

The advantages to Node Pointers include:
- The tree represents a hierachy of actual content, rather than the files containing the content.
- The tree permits nesting both within and beyond file level.
- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.



#### Duplicate Pointers  

Node Pointers may point more than once to the same node, so that content can be reused or referenced across multiple trees within the same project.
Here is the same example child node from above:  
Note that it appears twice in the Table of Contents, once as a child of this node and once as a child of this node's parent node ( [Pointers](#pointers)).




#### Recursive Node Pointers  

If the tree of a Node Pointer includes one of its own ancestors, the tree will stop at the recursion point with the indication `! RECURSION -` before the node title and link. For example, this Node Pointer points to the parent of this node ([Recursive Node Pointers](#recursive-node-pointers)),  |  ?  >>lmu. You can see the recursion point in the table of contents.

Note that if you view the tree with another node selected as root, one full iteration will still appear, with the point of recursion falling elsewhere. The tree below is turned "inside out", with [Pointers](#pointers) as root. 


(See [Trees](#trees) for how to generate trees like this in dynamic nodes.)



##### Example Recursive Node Tree

Pointers[Pointers](#pointers)
			├── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
			├── Duplicate Pointers[Duplicate Pointers](#duplicate-pointers)
			│   └── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
			└── Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
			    ├── ! RECURSION - (from alias) : Pointers[Pointers](#pointers)
			    └── Example Recursive Node Tree[Example Recursive Node Tree](#example-recursive-node-tree)









## Exporting
Urtext can export to plaintext, Markdown and HTML. Output can be written to a file or back into another node in the project. Exporting is dynamic; when changes are made to the source files, exports are immediately updated.



### Example : Urtext Documentation Exported in Markdown to a File  

This dynamic definition exports the entire documentation from its root node [Urtext  Version: 1.0-beta  Usage Guide and References](#urtext--version:-1.0-beta--usage-guide-and-references) ) in Markdown format to a file called [./README.md:](./README.md:)







### Example : Fragment Exported to HTML  

The following Dynamic Definition is identical to the above, except it exports to HTML.   







## File Naming                                                                                

Since node identities are independent of their filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

.txt

If no index is present:

.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.






## History

Though use of powerful version control tools (such as Git, Mercurial, etc.) is possible, Urtext has a lighter built-in versioning system that tracks edits at intervals. It is not necessary to make explicit "commits" in order to utilize this. Urtext creates a single, linear history of each file's content, with each snapshot being a "diff", or record of changes, since the previous snapshot. When a previous state is restored, no "checkout" or "rewind" occurs; rather, the newly restored state is appended to the history. Therefore, in addition to functioning as version control, the feature can also be used as an infinite and non-destructive "undo/redo" editing history that saves state when the file is closed. The default interval is 10 seconds, and can be modified in project_settings. 

To access a file's history, use [Toggle History Traverse: `ctrl + shift + g`](#toggle-history-traverse:-`ctrl-+-shift-+-g`).

Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.




## project_settingsThe `` node is optional. To create one, make a node and use metadata to give it the title `project_settings`:

This is the `project_settings` node for the "Urtext Documentation" Urtext project. In the metadata for this node you can specify a handful of settings for the project. (The text content of the node does not matter.)




### `title`  
Reserved key for every node, used here to specificy this node as containing project settings 




### `project_title`  
Provides a title for the entire project




### `home`  
Identifies the home node for the project, connected to the "Home" key 




### `console_log`  
(True or False): Sets whether Urtext will log updates, errors, messages to Sublime's Python console.
(Press Control-tilde(~)  to open the console) 





### `filenames`  
Specifies format for filenames when using [ MISSING LINK : pz9 ]  







### `timestamp_format` 	
Set the format of the timestamp when using [Insert Timestamp: `ctrl + shift + t`](#insert-timestamp:-`ctrl-+-shift-+-t`)
This accepts a Python `strftime` directive. For more information, see https://strftime.org/.








### `timezone`   

For a list of all timezones 
ADD SOME RESOURCE  




### `node_date_keyname`  











This node now has special reserved metadata keys that will be parsed as follows:
imestamp








## Errors and Warnings





[Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers)


## Using Multiple Projects

To use multiple projects at once, there is a project context manager. When you initially pass a path to Urtext, it looks recursively in all sub folders for additional projects. If it finds a compilable Urtext project in any one, it adds these to the context manager.  You can then freely switch among projects, either explicitly, or using links between the projects (described below). When switching projects, all Urtext's features, content and behavior, including links, compiling, and all functions linked to UI buttons, will operate in the context of the selected project. 

You can put all your Urtext projects into sub folders of a single path. Alternatively, you may put them anyplace in the file system and choose as your Urtext root a folder that encompasses them all. Compiling may take longer if Urtext has to search through many unused directories. 

Using Python, it is possible to only instantiate a single project, without the context manager. The current implementations in Sublime and Pythonista, however, use the context manager by default, even if you are only using a single project.

Recall that what defines a project is a folder. This is also what separates it from other projects. If you add other Urtext project folders into the initial path, they will all be accessible from the same project list.

To switch between projects in Sublime, select Urtext: Select Project from the command palette.
In Pythonista, use "Switch Projects" from the feature menu.



### Project Naming (Identification) 

Unlike nodes, projects are uniquely identified by name. For this reason, each project must have an unique name within the running instance of Urtext. Projects can be named using the project_title key in the project's project_settings node. If no name is present, the project's name becomes its absolute path in the file system. 





### Cross-Project Linking 

You may also link from one project to another within the text. To so this, use the following syntax:

=>"name or path of the other project[ MISSING LINK : idj ] 
(This link is only an example and is non-functioning)

Following this link will change the project context to the named project and open its specified node. 






## User Interface Elements

Urtext is made to require minimal user interface elements. They mostly serve as conveniences that duplicate 



### The Node Browser

The Node browser shows a list of all nodes in the project. It can be implemented in plaintext using a dynamic definition such as: . However, 

also be implemented 

Opening the Node List

Ctrl-Shift-E 




In Sublime Text there is also the alternative of using the UI dropdown. Press Control-Shift-E or select "Urtext: Node List" from the Sublime command palette (Shift-Super-P). Here you can find a node by typing part of its title.

In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see [`index`](#`index`)). 




### Traverse Mode   



This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.



#### Word Wrap in Traverse Mode 

Since Traverse Mode splits the window into two or more panes, it is suggested to set Word Wrap Column to "Auto" in Sublime Settings. This will cause the edited views to wrap correctly no matter the screen or window/pane size, as well as in Sublime's Distraction Free Mode.

Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.



