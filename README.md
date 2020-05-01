Urtext  Version: 0.2.0-alphaUrtext | Version: 0.2.0-alpha
Usage Guide and Reference
# Table of Contents
	Table of Contents 
	Urtext  Version: 0.2.0-alpha >a5m
	├── Quick Start and Guides >z7t
	│   ├── Urtext Syntax Guide >znj
	│   └── Urtext Action Guide >e1x
	├── About Urtext >013
	│   ├── Description >yv2
	│   ├── Comparison To Other Tools >h8z
	│   ├── Uses >lhs
	│   └── Project Requirements and Features >006
	├── Using this document >009
	│   ├── With Sublime Text >e6m
	│   └── Using Pythonista Urtext >lvf
	├── Setup >003
	│   ├── Making a New Project >dce
	│   │   └── Sublime >00a
	│   ├── Using/Adding Existing Files >00b
	│   │   ├── Sublime >rij
	│   │   ├── Pythonista >ouh
	│   │   └── Python >b44
	│   ├── Using a Sublime Project >c3n
	│   └── Sublime Text Interface Tips >000
	│       ├── Syntax Highlighting >01d
	│       ├── Hiding Tabs >015
	│       ├── Hiding Line Numbers >01e
	│       ├── Full Screen / Distraction Free Mode >002
	│       ├── Disable Prompts for File Reload >023
	│       └── Remove Indent Guides >1rc
	├── Nodes >01j
	│   ├── Node Identity (Node IDs) >01h
	│   ├── File Level Nodes >01g
	│   │   └── Creating a File Level Node >ekz
	│   │       ├── Sublime >xo8
	│   │       ├── Pythonista >xcx
	│   │       └── Python >83e
	│   ├── Inline Nodes >004
	│   │   ├── Example inline node >00e
	│   │   ├── Creating Inline Nodes >rbs
	│   │   │   ├── Sublime >8fh
	│   │   │   ├── Pythonista >hrv
	│   │   │   └── Python >fv2
	│   │   └── Syntax Highlighting of Inline Nodes (Sublime) >koe
	│   ├── Compact Nodes >kpz
	│   │   ├── Example Compact Node >d7b
	│   │   │   └── Example inline node within the compact node >9up
	│   │   └── Sublime >qwn
	│   │       └── Pythonista >0yn
	│   ├── Generating a node ID manually >rfp
	│   │   └── Sublime >7n6
	│   ├── Node Metadata >00x
	│   │   ├── Reserved Metadata Keys >011
	│   │   │   ├── title (overrides the default title) >00y
	│   │   │   ├── index >00z
	│   │   │   └── flags >cwb
	│   │   │       └── - exclude_from_tree >1e3
	│   │   └── Timestamps >005
	│   │       ├── Timeline View >00k
	│   │       └── Time Zones >7w6
	│   │           └── Timezone List >zh1
	│   └── The Node List >01i
	│       └── Opening the Node List >hl7
	│           └── Sublime >p78
	├── Trees >00h
	│   ├── From any given node >00f
	│   └── From the root >00g
	├── Links and Pointers >00j
	│   ├── Links >0y2
	│   │   └── Sublime Text tools to help with linking >00m
	│   ├── Dynamically Titled Links >4vu
	│   ├── Opening Links >01w
	│   │   ├── Sublime >osu
	│   │   └── Pythonista >iy8
	│   ├── Viewing Linked Relationships >00u
	│   ├── Linking to outside resources >00q
	│   │   ├── Web >00o
	│   │   └── Files >00p
	│   ├── Pointers >lmu
	│   │   ├── Duplicate Pointers >00t
	│   │   │   └── Example Child Node Using a Node Pointer >001
	│   │   └── Recursive Node Pointers >6ct
	│   │       ├── ? (Missing Node): >! RECURSION 2:a5m
	│   │       └── Example Recursive Node Tree >01n
	│   └── Traverse Mode >00w
	│       └── Word Wrap in Traverse Mode >xci
	├── Using Multiple Projects at a Time >ipy
	│   ├── Project Naming (Identification) >tgp
	│   └── Linking Between Projects >7lx
	├── Converting and Exporting >ezg
	│   ├── Example : Urtext Documentation Exported in Markdown to a File >m9d
	│   └── Example : Fragment Exported to HTML >baq
	├── Search >k67
	│   └── Full Text Search >4p9
	│       ├── Searching >mzj
	│       │   ├── Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lowe >k8v
	│       │   └── Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind the >q8j
	│       └── Search Using Dynamic Nodes >uy4
	├── Filenames >01m
	├── Development >01o
	│   └── Make Installation Easier >mh8
	└── File History >prp
# Quick Start and Guides  
## Urtext Syntax GuideUrtext Syntax Guide

Text is plain content unless inside a metadata wrapper, timetamp wrapper, or dynamic definition wrapper. The following syntax applies:
[Links](#links)	Link to another node by ID. 
More information: [Links](#links)

| 		Placed before a node link, dynamically populates the node title. 
Example and more info: [Dynamically Titled Links](#dynamically-titled-links)

>>xxx	Node Pointer
Embeds the specified node as though it were included inline using
More information: [Pointers](#pointers)
More information: [Compact Nodes](#compact-nodes)
Subnode	wrapper. Can appear anywhere. Can be nested aribrarily deep.
More information: [Inline Nodes](#inline-nodes)

Metadata wrapper

Example:



Dynamic Definition Wrapper. 

Template:


Examples:

## Urtext Action Guide

Navigation:

Home
Navigate Forward
Navigate Back

Export

Timeline

Node List

Search

Traverse Mode

Multiple Projects

Jump to Source

File History

Interlinks

Tree

Consolidate Metadata

Import Project

Reload Project

Reindex All Files

Rename File(s) from Meta

Delete This Node

Initialize Project

Pop Node

Move File to Other Project

Node Access History

# About Urtext
## Description 

Urtext is a syntax and interpreter for plaintext. Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A collection of nodes constitutes a "project"; the interpreter is aware of all the nodes in a project at once, so that nodes can reference, modify, and organize one another, across hundreds or thousands of files. The syntax permits embedding of structural and instructional code into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python is running. Equivalent or variant interpreters could be created in any language or editing environment. Using Urtext in a text editor requires an additional wrapper to pass messages between the text editor and Urtext. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).
## Comparison To Other Tools 

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. Though it can be made to export to HTML, Urtext is not primarily a document conversion or document generation tool. It is rather a tool for organizing text.

Urtext consolidates content, markup and instructions (scripting) into a single compilable syntax. Though it can hyperlink many documents or parts of documents together, unlike HTML, there is no additional code or markup "behind" the visible content. Everything the interpreter reads is visible at all times.
## Uses  

Urtext has many uses, including but limited to:

- prose writing
- research
- documentation
- knowledge/information base
- journaling
- Zettelkasten
- project/personal organization
- notetaking
- any other writing or information management that can be done in text form
## Project Requirements and Features   

Many of the following features and benefits were core requirements when creating Urtext. Others came about indirectly. Though many can be found in other tools, they cannot be found together in one single existing tool; this was the motivation for creating Urtext.

- It uses plain text files. Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof.

- It can compile, organize, and link content spread across hundreds or thousands of files.

- Urtext files and content elements can be linked to one another in tree-like, recursive (tangled), and other non-hierarchical ways.

- It has customizable and extensible metadata that does not rely on the file system.

- It is decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

- It is usable across multiple platforms and devices.

- It can incorporate other plaintext syntaxes, including other markup languages and programming languages.

- There is no need to interact directly with the file system (creating, naming, saving, organizing files). File creation, naming and management is handled for you, unless you want to manually name files.

- Cascading complexity; use only the parts you need. Does not take months/years to learn.

- Future-proof. No reliance on anything that may not exist in 5 or 100 years. Urtext files themselves are in plaintext, which will never become unusable. The interpreter/compiler could theoretically be implemented in any sufficiently capable language desired, current, past or future.

- Does not depend on a cloud service. Though cloud services can be used to sync project files among devices, the interpreter itself is made to operate locally; content wholly resides on the device being used.

- Being open source, Urtext is extensible, hackable and customizable to specific needs.

Being in plaintext and having a syntax specification, it can also be used with:

- Themes and syntax highlighting.

- Version control (using Git, for example).

# Using this document  

This is a documentation of Urtext, written and compiled in Urtext. It can be used as both a reference manual and an example project. If you're reading this on Github, the `README.MD` file was generated from the Urtext files in this repository. The repository itself is an Urtext project that can be cloned/downloaded.
## With Sublime Text 

- First set up Urtext in Sublime. Follow the instructions at [Dependencies and Installation (Sublime)](#dependencies-and-installation-sublime)
- Clone/download this repository and open it up in Sublime. It will automatically be read as an Urtext project when you can navigate. To get started quickly, follow these tips, which are described in greater detail in their respective sections of this documentation.

- To go to a link in the table of contents, press ctrl-shift-/ from any line. Links are three-character node-IDs preceded by one or two right-angle brackets. (See [Links and Pointers](#links-and-pointers) for more information).
- To return to this table of contents, press ctrl-shift-H.
- You can also traverse the table of contents while viewing linked content in another pane using Traverse Mode : Press Ctrl-Shift-R and click or arrow-navigate to any node in the table. See [Traverse Mode](#traverse-mode) for more information.
- Enabling syntax highlighting makes the documentation much easier to read: Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ...  Then switch to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.) See  [Syntax Highlighting](#syntax-highlighting) for more information.
- See [Sublime Text Interface Tips](#sublime-text-interface-tips) for other suggestions.
## Using Pythonista Urtext 

- Set up Urtext in Pythonista. Follow the instructions in [Pythonista Urtext Implementation Setup](#pythonista-urtext-implementation-setup)
- Clone the documentation repository into your base Urtext path and it will be accessible from within Pythonista Urtext.
# Setup

## Sublime Text Implementation Setup 

The Urtext package for Sublime Text utilizes Sublime's embedded Python 3.3 interpreter both to run the Urtext interpreter/compiler and to add features to Sublime that make working with Urtext easy:

- binds many Urtext operations to the Sublime command palette
- adds key bindings (hotkeys) as shortcuts for some features
- leverages the built-in Sublime browser/palette for Urtext project navigation
- defines a syntax for use with Sublime's color schemes
- adds Urtext syntax highlighting to two of Sublime's default color schemes (Monokai and Sixteen)
- adds filebrowser-like project navigation using [Traverse Mode](#traverse-mode)

Some features in this documentation are built into the Urtext interpreter/compiler, while others are part of only the Sublime Text implementation. Features that are specific to Sublime are tagged with the keyword `sublime`.
### Dependencies and Installation (Sublime)     

The decision has been made not to include Urtext or its dependencies in the Urtext package for Sublime. It is necessary to install everything manually into Sublime's Python 3.3 environment. This is in fact less complicated than the current alternatives considered. For developers, see [Make Installation Easier](#make-installation-easier).

To use Urtext in Sublime Text:

- Install Sublime Text ( https://www.sublimetext.com/ )

- Clone or download Sublime Urtext ( https://github.com/nbeversl/urtext_sublime ). Place it in your Packages folder (Sublime Text 3/Packages). The package is not yet available in Package Control. 

- Add Urtext and all its dependencies to Sublime's Python interpreter. There are two options for doing this:
#### Download and Install Dependencies Manually  

- anytree
https://github.com/c0fec0de/anytree
The folder needed is `anytree` inside this download; add it to `Sublime Text 3/Lib/python3.3`.

- pytz
https://pypi.org/project/pytz/
The folder needed is `pytz`; add it to `Sublime Text 3/Lib/python3.3`.

- six
https://pypi.org/project/six/
The only FILE needed is `six.py`, nothing else; add this directly to `Sublime Text 3/Lib/python3.3`.

- urtext 
https://github.com/nbeversl/urtext
This is Urtext itself. Put the entire folder (`urtext`) into `Sublime Text 3/Lib/python3.3`.

- fuzzywuzzy 
https://github.com/seatgeek/fuzzywuzzy
The folder needed is `fuzzywuzzy`; add it to `Sublime Text 3/Lib/python3.3`.

- diff-match-patch
The folder needed is `diff_match_patch`; add it to `Sublime Text 3/Lib/python3.3`.
https://pypi.org/project/diff-match-patch/
#### Download Dependencies from a Monorepo  

As a convenience, all of the above depenencies are (for now) maintained in recent versions at https://github.com/nbeversl/urtext_deps, with all files in the path locations described above. Download this repository as a .ZIP file, unzip it, and drop its contents into your `Sublime Text 3/Lib/python3.3` folder.
Close and reopen Sublime Text. Urtext is now ready to use.
  
## Pythonista Urtext Implementation Setup

Urtext can be run on iOS devices using the Pythonista app, which provides a full Python interpreter inside of iOS. 
This implementation utilizes the native iOS user interface to create a basic text editor view, along with buttons bound to Urtext's functions (similar to the keyboard shortcut bindings in Sublime), project navigation funtions, and syntax highlighting matching those found in the Sublime Text implementation. Using iCloud, projects can be synced among iOS devices and other devices (desktops, laptops). Once synced, a copy of the project resides fully on the device and is not dependent on a live data connection (see [Project Requirements and Features](#project-requirements-and-features)).

- Install Pythonista (http://omz-software.com/pythonista/)

- Clone or download the Urtext-Pythonista package (https://github.com/nbeversl/urtext_pythonista).

- Install all the above mentioned Python dependencies into your Pythonista environment.( [Download and Install Dependencies Manually](#download-and-install-dependencies-manually) )

- (optional) To launch or switch to Urtext using an app icon, use the Shortcuts app.

## Making a New Project
### Sublime	


To make an empty project, make a new folder (or open an existing folder, if you want to create a new project there) and open the folder in Sublime. Select Urtext : Initialize Project from the Sublime Command Palette. Then press Ctrl-Shift-; to create a new node.

Pythonista

not currently implemented. Use an existing project.
## Using/Adding Existing Files 

To use existing plaintext files, you must add minimally an `ID` ([More About Node IDs](#more-about-node-ids)) metadata tag to the file's text content. See [Node Metadata](#node-metadata) for more information on Metadata.
### Sublime   

Select `Urtext : Import Project` from the Sublime Command palette.

Note that the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.
### Pythonista 

Not currently implemented.
### Python   

Pass the keyword argument `import_project=True`:

%%-PYTHON

from urtext.project import UrtextProject
path = '~/users/someone/path/to/project/folder'
my_project = UrtextProject(path, import_project=True)

%%-END
## Using a Sublime Project   

(not to be confused with an Urtext Project -- see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.  

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.
## Sublime Text Interface Tips  

Here are some tips for best leveraging Sublime's great UI features.
### Syntax Highlighting 

This package comes with a .YML file (`sublime_urtext.sublime_syntax`) defining the Urtext syntax, along with two color schemes that provide syntax highlighting. Syntax highlighting makes everything easier by showing depth of node nesting and dimming certain elements of the syntax. Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ... 

Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.)
### Hiding Tabs	

If you prefer a clean, terminal-like view, hide tabs: View -> Hide Tabs
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation.
### Hiding Line Numbers  

For an extra-clean look, hide line numbers by adding:
"settings" : {
"line_numbers": false,
},

... to your Sublime project settings file.
### Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode
### Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
"settings" : {
"always_prompt_for_file_reload": false,
},
### Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:

"settings" : {
"draw_indent_guides": false,
}

# Nodes

Think of a node as a region of paper with flexible and open-ended length.
## Node Identity (Node IDs) 

The identity of an Urtext node persists no matter its containing filename, even when moved from one file to another. This is accomplished by assigning each node a unique identifier. Since nothing is hidden from view in an Urtext file, a minimally intrusive format of three alphanumeric was chosen. This results in over 46,000 possible nodes per project. Every node must have an ID; files with nodes missing IDs cannot be compiled and are omitted from the project. Each node's ID is generated automatically on creation and placed into its initial metadata region. ID's can be changed without affecting functionality, though pre-existing links must be manually changed as well. IDs are not case sensitive.

Node IDs are assigned in random order and have no special meaning except as a unique identifier. IDs are covered more in [More About Node IDs](#more-about-node-ids).
## File Level Nodes 

A file-level node is any node at the outermost level of a single file. It may or may not contain other nodes nested inside it.
### Creating a File Level Node
#### Sublime  

Press Control-Shift-; (Control-Shift-semicolon).
#### Pythonista  

Press `;` in the Urtext key row.
#### Python 

%%-PYTHON

UrtextProject.new_file_node(date=None, metadata = {}, node_id=None)
"""
Kwargs:
date (datetime): the timestamp, defaults to now if not specified
metadata (dict): key/value metadata pairs
node_id (str): optionally specify a node_id (rarely used)
Returns:
dict: { 'filename' : # (str) : the new filename, without path
'id': # (str) the new node_id 
}
"""

%%-END
The file is created, named and saved automatically. It has whitespace on top and a metadata block at the bottom containing a node ID and a timestamp of the creation date and time.
By default, the first non-whitespace line of any node is the node's title. Write a title and anything else into the node. Save it as usual (Super-S in Sublime).
## Inline Nodes                                                                 

Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another inline node. The syntax for inline nodes is to wrap the content in double curly braces:
### Example inline node
.
### Creating Inline Nodes
#### Sublime   

Press Shift-Ctrl-{ . Inside the inserted double curly braces is a new node with an auto-generated ID. 

To wrap existing content into an inline node, first select the content and use the same keypress.

You can also do this manually by typing the curly braces generating a new metadata region with an ID by pressing Control-Shift-I.
#### Pythonista  

Press the curly-braces `{ {` in the Urtext key row.
#### Python  

%%-PYTHON

UrtextProject.add_inline_node(date=None, contents='', metadata={}, one_line=False)

"""
Kwargs:
date (datetime): optional timestamp
contents (str): optional initial contents
metadata (dict): optional key/value metadata pairs
one_line (Boolean): Whether the wrapper and metadata should be consolidated on a single line
Returns:
string: the contents of the new node, which can then be manually inserted using a text editor.

This is mostly a utility function to generate text that can otherwise be written manually. Since this has to be done in any Urtext implementation, it is included as a method. It also generates a unique node ID and adds the node to the project object.
"""

%%-END
Unlike a word processor, Urtext requires attention to syntax. Every opening doubly curly bracket must be closed in the same file and requires an ID metadata tag between its opening an closing brackets.

NOTE that file-level nodes [File Level Nodes](#file-level-nodes)) do not use curly-braces, as their boundaries are defined by the file itself.

For all purposes in Urtext, inline nodes' metadata and identity is unique from their containing file and parent nodes.
### Syntax Highlighting of Inline Nodes (Sublime)  

In Sublime, when syntax highlighting is used [Syntax Highlighting](#syntax-highlighting)), inline nodes will have background shading showing nesting up to five layers deep. More levels can be added, if you need them, by altering sublime_urtext.sublime-syntax.

## Compact Nodes

For contents requiring only a single line, such as list items, very short notes, and similar entries, use the caret character (`^`) as the first non-whitesoace character on a new line. This defines a new node as a child of the node in which the ^ character appears, with the closing wrapper being the end of the same line. Note that, like all nodes, a compact node must contain an ID, and can contain any other metadata. It can even include inline nodes, as long as their entire contents, including wrapper and metadata, are contained on a single line.

(Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)
### Example Compact Node
#### Example inline node within the compact node

## Generating a node ID manually
### Sublime 	   

If you accidentally delete a Node ID or need to insert one arbitrarily, press Control-Shift-I. 

Pythonista 

Not current implemented

Python  

%%-PYTHON

UrtextProject.next_index()
"""
Returns: 
string : An unused node ID in the project.
"""

%%-END

## Node Metadata

Metadata is data about the content, in the form of key/value pairs and timestamps. Other than a few reserved key/value pairs used for compiling, metadata is open for user-defined purposes. Keys and values of metadata tags are indexed automatically and searchable within the Urtext project (see[ MISSING LINK : 012 ] ). 

Metadata regions in Urtext open with a forward-slash followed by two dashes and close with two dashes followed by a forward slash. Each metadata entry is a key/value pair, separated by a colon, with the value containing an optional timestamp. Examples:




The only required metadata is a node ID. Additional user-defined metadata can be added into the same region, and additional metadata regions can be inserted arbitrarily anywhere inside a node. You can also string several entries together on one line, separated by semicolons:



Note that: 

-   A colon separates the key from the value 

-   All three components are optional; any content preceding a colon (if one is present) is interpreted as a key; content following the (first) colon is interpreted as a value. If no colon is present, the entry is read as a key with an empty value.

-   A timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexed.

-   Values are not case-sensitive, except for the values of the following keys:

title
notes
timestamp_format 
( used in the project_settings node only : see[project_settings](#project_settings))
filenames
### Reserved Metadata Keys 

There are three reserved metadata keys:
#### title (overrides the default title)   title

If you want to override the automatic title and assign a title manually, use title tag in the metadata block:
#### index   

You can optionally add a two-digit sort index (00-99) to a node, such as:



Index tags will sort the files in the Node List [The Node List](#the-node-list)) . Any indexed nodes will sort before (above) the others, with lowest number appearing first. 

Remember unindexed notes display in order of creation, newest first, based on the value of the timestamp. You can give the same index number to multiple nodes; in this case they sort with the most recent node first, within each index.
#### flags  

The `flags` key is used to set node behavior. At present only the following exists:
##### - exclude_from_tree

Excludes a node from being included in a tree. For an example, see Example 2 in "Dynamic Nodes"[Example 2 : Tree](#example-2-:-tree). For more on tree, see[Trees](#trees)
The only additional reserved metadata keys apply only to the project_settings node [project_settings](#project_settings)).
Next topics:

### Timestamps                                                                                  

Reliance on the operating system's file-created or file-modified date metadata is avoided, since it can be too easily and involuntarily overwritten under ordinary file system operations, such as copying and moving files or folders. 

Text between two angled brackets (<  >) is interpreted as a timestamp. 

To insert a timestamp in Sublime, press Control-Shift-O. 

Node timestamps are part of metadata (see Metadata[Node Metadata](#node-metadata)). Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.

Timestamps are read and written utilizing Python's `strftime` directives. The default format is:

%%-PYTHON
`.%a., %b. %d, %Y, %I:%M %p`
%%-END

which creates timestamps like: <Tue., Jun. 04, 2019, 08:51 PM>. The format can be customized in the project_settings node (see project_settings[project_settings](#project_settings)). For more information on `strftime` directives and options, see https://docs.python.org/2/library/datetime.html#strftime-and-strptime-behavior.
#### Timeline View   

Urtext will parse node timestamps along with inline timestamps into a project timeline. Press Ctrl-Shift-T or select Urtext: Show Timeline in the Sublime command palette. Each node and inline timestamp is shown in chronological order with nearby text. You can try it with this example project, but note that since many nodes in this document are undated, they have a default date of Thu., Jan. 01, 1970, 12:00AM.

As everywhere in a project, node IDs shown are links that can be opened using Ctrl-Shift-/.
#### Time Zones 	  

Time zones are not required in timestamps. If no time zone is present, Coordinated Universal Time (UTC) is added by default for parsing and comparison purposes. To modify this default, set the `timezone` key in project settings to another valid value. (Timezone List ##### Timezone List

Africa/Abidjan
Africa/Accra
Africa/Addis_Ababa
Africa/Algiers
Africa/Asmara
Africa/Asmera
Africa/Bamako
Africa/Bangui
Africa/Banjul
Africa/Bissau
Africa/Blantyre
Africa/Brazzaville
Africa/Bujumbura
Africa/Cairo
Africa/Casablanca
Africa/Ceuta
Africa/Conakry
Africa/Dakar
Africa/Dar_es_Salaam
Africa/Djibouti
Africa/Douala
Africa/El_Aaiun
Africa/Freetown
Africa/Gaborone
Africa/Harare
Africa/Johannesburg
Africa/Juba
Africa/Kampala
Africa/Khartoum
Africa/Kigali
Africa/Kinshasa
Africa/Lagos
Africa/Libreville
Africa/Lome
Africa/Luanda
Africa/Lubumbashi
Africa/Lusaka
Africa/Malabo
Africa/Maputo
Africa/Maseru
Africa/Mbabane
Africa/Mogadishu
Africa/Monrovia
Africa/Nairobi
Africa/Ndjamena
Africa/Niamey
Africa/Nouakchott
Africa/Ouagadougou
Africa/Porto-Novo
Africa/Sao_Tome
Africa/Timbuktu
Africa/Tripoli
Africa/Tunis
Africa/Windhoek
America/Adak
America/Anchorage
America/Anguilla
America/Antigua
America/Araguaina
America/Argentina/Buenos_Aires
America/Argentina/Catamarca
America/Argentina/ComodRivadavia
America/Argentina/Cordoba
America/Argentina/Jujuy
America/Argentina/La_Rioja
America/Argentina/Mendoza
America/Argentina/Rio_Gallegos
America/Argentina/Salta
America/Argentina/San_Juan
America/Argentina/San_Luis
America/Argentina/Tucuman
America/Argentina/Ushuaia
America/Aruba
America/Asuncion
America/Atikokan
America/Atka
America/Bahia
America/Bahia_Banderas
America/Barbados
America/Belem
America/Belize
America/Blanc-Sablon
America/Boa_Vista
America/Bogota
America/Boise
America/Buenos_Aires
America/Cambridge_Bay
America/Campo_Grande
America/Cancun
America/Caracas
America/Catamarca
America/Cayenne
America/Cayman
America/Chicago
America/Chihuahua
America/Coral_Harbour
America/Cordoba
America/Costa_Rica
America/Creston
America/Cuiaba
America/Curacao
America/Danmarkshavn
America/Dawson
America/Dawson_Creek
America/Denver
America/Detroit
America/Dominica
America/Edmonton
America/Eirunepe
America/El_Salvador
America/Ensenada
America/Fort_Nelson
America/Fort_Wayne
America/Fortaleza
America/Glace_Bay
America/Godthab
America/Goose_Bay
America/Grand_Turk
America/Grenada
America/Guadeloupe
America/Guatemala
America/Guayaquil
America/Guyana
America/Halifax
America/Havana
America/Hermosillo
America/Indiana/Indianapolis
America/Indiana/Knox
America/Indiana/Marengo
America/Indiana/Petersburg
America/Indiana/Tell_City
America/Indiana/Vevay
America/Indiana/Vincennes
America/Indiana/Winamac
America/Indianapolis
America/Inuvik
America/Iqaluit
America/Jamaica
America/Jujuy
America/Juneau
America/Kentucky/Louisville
America/Kentucky/Monticello
America/Knox_IN
America/Kralendijk
America/La_Paz
America/Lima
America/Los_Angeles
America/Louisville
America/Lower_Princes
America/Maceio
America/Managua
America/Manaus
America/Marigot
America/Martinique
America/Matamoros
America/Mazatlan
America/Mendoza
America/Menominee
America/Merida
America/Metlakatla
America/Mexico_City
America/Miquelon
America/Moncton
America/Monterrey
America/Montevideo
America/Montreal
America/Montserrat
America/Nassau
America/New_York
America/Nipigon
America/Nome
America/Noronha
America/North_Dakota/Beulah
America/North_Dakota/Center
America/North_Dakota/New_Salem
America/Ojinaga
America/Panama
America/Pangnirtung
America/Paramaribo
America/Phoenix
America/Port-au-Prince
America/Port_of_Spain
America/Porto_Acre
America/Porto_Velho
America/Puerto_Rico
America/Rainy_River
America/Rankin_Inlet
America/Recife
America/Regina
America/Resolute
America/Rio_Branco
America/Rosario
America/Santa_Isabel
America/Santarem
America/Santiago
America/Santo_Domingo
America/Sao_Paulo
America/Scoresbysund
America/Shiprock
America/Sitka
America/St_Barthelemy
America/St_Johns
America/St_Kitts
America/St_Lucia
America/St_Thomas
America/St_Vincent
America/Swift_Current
America/Tegucigalpa
America/Thule
America/Thunder_Bay
America/Tijuana
America/Toronto
America/Tortola
America/Vancouver
America/Virgin
America/Whitehorse
America/Winnipeg
America/Yakutat
America/Yellowknife
Antarctica/Casey
Antarctica/Davis
Antarctica/DumontDUrville
Antarctica/Macquarie
Antarctica/Mawson
Antarctica/McMurdo
Antarctica/Palmer
Antarctica/Rothera
Antarctica/South_Pole
Antarctica/Syowa
Antarctica/Troll
Antarctica/Vostok
Arctic/Longyearbyen
Asia/Aden
Asia/Almaty
Asia/Amman
Asia/Anadyr
Asia/Aqtau
Asia/Aqtobe
Asia/Ashgabat
Asia/Ashkhabad
Asia/Baghdad
Asia/Bahrain
Asia/Baku
Asia/Bangkok
Asia/Barnaul
Asia/Beirut
Asia/Bishkek
Asia/Brunei
Asia/Calcutta
Asia/Chita
Asia/Choibalsan
Asia/Chongqing
Asia/Chungking
Asia/Colombo
Asia/Dacca
Asia/Damascus
Asia/Dhaka
Asia/Dili
Asia/Dubai
Asia/Dushanbe
Asia/Gaza
Asia/Harbin
Asia/Hebron
Asia/Ho_Chi_Minh
Asia/Hong_Kong
Asia/Hovd
Asia/Irkutsk
Asia/Istanbul
Asia/Jakarta
Asia/Jayapura
Asia/Jerusalem
Asia/Kabul
Asia/Kamchatka
Asia/Karachi
Asia/Kashgar
Asia/Kathmandu
Asia/Katmandu
Asia/Khandyga
Asia/Kolkata
Asia/Krasnoyarsk
Asia/Kuala_Lumpur
Asia/Kuching
Asia/Kuwait
Asia/Macao
Asia/Macau
Asia/Magadan
Asia/Makassar
Asia/Manila
Asia/Muscat
Asia/Nicosia
Asia/Novokuznetsk
Asia/Novosibirsk
Asia/Omsk
Asia/Oral
Asia/Phnom_Penh
Asia/Pontianak
Asia/Pyongyang
Asia/Qatar
Asia/Qyzylorda
Asia/Rangoon
Asia/Riyadh
Asia/Saigon
Asia/Sakhalin
Asia/Samarkand
Asia/Seoul
Asia/Shanghai
Asia/Singapore
Asia/Srednekolymsk
Asia/Taipei
Asia/Tashkent
Asia/Tbilisi
Asia/Tehran
Asia/Tel_Aviv
Asia/Thimbu
Asia/Thimphu
Asia/Tokyo
Asia/Tomsk
Asia/Ujung_Pandang
Asia/Ulaanbaatar
Asia/Ulan_Bator
Asia/Urumqi
Asia/Ust-Nera
Asia/Vientiane
Asia/Vladivostok
Asia/Yakutsk
Asia/Yekaterinburg
Asia/Yerevan
Atlantic/Azores
Atlantic/Bermuda
Atlantic/Canary
Atlantic/Cape_Verde
Atlantic/Faeroe
Atlantic/Faroe
Atlantic/Jan_Mayen
Atlantic/Madeira
Atlantic/Reykjavik
Atlantic/South_Georgia
Atlantic/St_Helena
Atlantic/Stanley
Australia/ACT
Australia/Adelaide
Australia/Brisbane
Australia/Broken_Hill
Australia/Canberra
Australia/Currie
Australia/Darwin
Australia/Eucla
Australia/Hobart
Australia/LHI
Australia/Lindeman
Australia/Lord_Howe
Australia/Melbourne
Australia/NSW
Australia/North
Australia/Perth
Australia/Queensland
Australia/South
Australia/Sydney
Australia/Tasmania
Australia/Victoria
Australia/West
Australia/Yancowinna
Brazil/Acre
Brazil/DeNoronha
Brazil/East
Brazil/West
CET
CST6CDT
Canada/Atlantic
Canada/Central
Canada/East-Saskatchewan
Canada/Eastern
Canada/Mountain
Canada/Newfoundland
Canada/Pacific
Canada/Saskatchewan
Canada/Yukon
Chile/Continental
Chile/EasterIsland
Cuba
EET
EST
EST5EDT
Egypt
Eire
Etc/GMT
Etc/GMT+0
Etc/GMT+1
Etc/GMT+10
Etc/GMT+11
Etc/GMT+12
Etc/GMT+2
Etc/GMT+3
Etc/GMT+4
Etc/GMT+5
Etc/GMT+6
Etc/GMT+7
Etc/GMT+8
Etc/GMT+9
Etc/GMT-0
Etc/GMT-1
Etc/GMT-10
Etc/GMT-11
Etc/GMT-12
Etc/GMT-13
Etc/GMT-14
Etc/GMT-2
Etc/GMT-3
Etc/GMT-4
Etc/GMT-5
Etc/GMT-6
Etc/GMT-7
Etc/GMT-8
Etc/GMT-9
Etc/GMT0
Etc/Greenwich
Etc/UCT
Etc/UTC
Etc/Universal
Etc/Zulu
Europe/Amsterdam
Europe/Andorra
Europe/Astrakhan
Europe/Athens
Europe/Belfast
Europe/Belgrade
Europe/Berlin
Europe/Bratislava
Europe/Brussels
Europe/Bucharest
Europe/Budapest
Europe/Busingen
Europe/Chisinau
Europe/Copenhagen
Europe/Dublin
Europe/Gibraltar
Europe/Guernsey
Europe/Helsinki
Europe/Isle_of_Man
Europe/Istanbul
Europe/Jersey
Europe/Kaliningrad
Europe/Kiev
Europe/Kirov
Europe/Lisbon
Europe/Ljubljana
Europe/London
Europe/Luxembourg
Europe/Madrid
Europe/Malta
Europe/Mariehamn
Europe/Minsk
Europe/Monaco
Europe/Moscow
Europe/Nicosia
Europe/Oslo
Europe/Paris
Europe/Podgorica
Europe/Prague
Europe/Riga
Europe/Rome
Europe/Samara
Europe/San_Marino
Europe/Sarajevo
Europe/Simferopol
Europe/Skopje
Europe/Sofia
Europe/Stockholm
Europe/Tallinn
Europe/Tirane
Europe/Tiraspol
Europe/Ulyanovsk
Europe/Uzhgorod
Europe/Vaduz
Europe/Vatican
Europe/Vienna
Europe/Vilnius
Europe/Volgograd
Europe/Warsaw
Europe/Zagreb
Europe/Zaporozhye
Europe/Zurich
GB
GB-Eire
GMT
GMT+0
GMT-0
GMT0
Greenwich
HST
Hongkong
Iceland
Indian/Antananarivo
Indian/Chagos
Indian/Christmas
Indian/Cocos
Indian/Comoro
Indian/Kerguelen
Indian/Mahe
Indian/Maldives
Indian/Mauritius
Indian/Mayotte
Indian/Reunion
Iran
Israel
Jamaica
Japan
Kwajalein
Libya
MET
MST
MST7MDT
Mexico/BajaNorte
Mexico/BajaSur
Mexico/General
NZ
NZ-CHAT
Navajo
PRC
PST8PDT
Pacific/Apia
Pacific/Auckland
Pacific/Bougainville
Pacific/Chatham
Pacific/Chuuk
Pacific/Easter
Pacific/Efate
Pacific/Enderbury
Pacific/Fakaofo
Pacific/Fiji
Pacific/Funafuti
Pacific/Galapagos
Pacific/Gambier
Pacific/Guadalcanal
Pacific/Guam
Pacific/Honolulu
Pacific/Johnston
Pacific/Kiritimati
Pacific/Kosrae
Pacific/Kwajalein
Pacific/Majuro
Pacific/Marquesas
Pacific/Midway
Pacific/Nauru
Pacific/Niue
Pacific/Norfolk
Pacific/Noumea
Pacific/Pago_Pago
Pacific/Palau
Pacific/Pitcairn
Pacific/Pohnpei
Pacific/Ponape
Pacific/Port_Moresby
Pacific/Rarotonga
Pacific/Saipan
Pacific/Samoa
Pacific/Tahiti
Pacific/Tarawa
Pacific/Tongatapu
Pacific/Truk
Pacific/Wake
Pacific/Wallis
Pacific/Yap
Poland
Portugal
ROC
ROK
Singapore
Turkey
UCT
US/Alaska
US/Aleutian
US/Arizona
US/Central
US/East-Indiana
US/Eastern
US/Hawaii
US/Indiana-Starke
US/Michigan
US/Mountain
US/Pacific
US/Pacific-New
US/Samoa
UTC
Universal
W-SU
WET
Zulu
)


## The Node List

Every project maintains a list of all its nodes. The Node List is automatically written to a built-in file-level dynamic node. (See [ MISSING LINK : e82 ]  for more information).
### Opening the Node List
#### Sublime 	  

Ctrl-Shift-J. Like any node, the Node List can be traversed using [Traverse Mode](#traverse-mode).

Pythonista  

Urtext Keys: L

The Pythonista Urtext app also contains a Node Browser with fuzzy search. Press ? and type a node title.

Python 

Get the filename by passing node ID 'zzy' to get_file_name() method and open it directly:

%%-PYTHON
UrtextProject.get_file_name(node_id)
"""
Args:
node_id (string) : Node ID=
Returns:
string : filename **WITHOUT** path
or None
"""
%%-END
In Sublime Text there is also the alternative of using the UI dropdown. Press Control-Shift-E or select "Urtext: Node List" from the Sublime command palette (Shift-Super-P). Here you can find a node by typing part of its title.

In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see [index](#index)). 

The Node ID `zzz` is reserved for the Node list. (See [Node Identity (Node IDs)](#node-identity-node-ids) for more information.)


# Trees

In Sublime, you can view a tree of node hierarchies in two ways:
## From any given node 

Position the cursor in the node you want to see as root (outermost) and select "Urtext: Show Tree From Current Node" from the Sublime Command Palette. This will add a new split view to the left side of the current view in Sublime, containing a tree with the selected node as root.
## From the root  

Position the cursor anywhere in the node/file and select "Urtext: Show Tree From Root". This will do the same as above, but the tree will include everything back to the node's root. If the tree extends upward beyond the current file, that will also be included.
Note that each branch of the resulting file tree contains Node ID that works like a link. You can navigate the links on the tree using Shift-Control-/ (see [Links](#links)) or using [Traverse Mode](#traverse-mode).

File trees are displayed in Sublime's scratch views, meaning they will never report as being "dirty" (unsaved). They are intended for one-time/temporary use, will not have a filename, and will not update when a node/file changes. To make permanent and dynamically updated trees, see [ MISSING LINK : e82 ] .

You can extend node trees beyond the file level by using [Pointers](#pointers).

Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.

# Links and Pointers
## Links   

To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.
### Sublime Text tools to help with linking   

Two Sublime Command Palette commands can make linking quick and easy:

Urtext : Link To ...
Links from the currently viewed node to another node which you can select in the selection panel. When you select a node in the quick panel, a link to that node will be inserted at the cursor.

Urtext: Link From ...
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.
## Dynamically Titled Links  

Prepending a pipe character to any node link will populate the space between the pipe and link with the node's title, from its metadata or default title. Examples are found throughout this documentation. 

Note that node link titles are not updated globally throughout the project whenever any node's title changes; rather, titled links are updated at the single file level whenever that file is saved.
## Opening Links
### Sublime 

Press Shift-Ctrl-/ on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point.
### Pythonista  

Use the `>` key when the cursor is on any line containing a link.
Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save.
## Viewing Linked Relationships

Elaborate writing and reference systems such as wikis often linking nodes together in tangled and intricate ways. While Urtext cannot draw diagrams of this kind (called acyclic graphs) in plaintext, it can represent these relationships from the perspective of any one node: Position the cursor in the desired node and select "Urtext : Show Linked Relationships..." The currently selected node will be displayed as root; all nodes linking into this nodes, and recursively into those nodes, will be displayed above the root; all files linked from this node, and recursively from those nodes, will be displayed below. Circular references are represented up to one iteration.

These diagrams are displayed as Sublime "scratch" views, meaning they will never report as being dirty (unsaved). They are intended for one-time/temporary use and will not update when a node/file changes. To make permanent and dynamically updated diagrams, see [ MISSING LINK : e82 ] .

## Linking to outside resources
### Web 

HTTP links are recognized automatically and will open in the default browser.

Example: http://fantutti.com
### Files 

COMING.

## Pointers          

You can extend trees beyond the file level to create node relationships spanning many files. Preceding a link to a node with two right angle brackets instead of one creates a Pointer. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as children of the node containing the Pointer. Example:

Here is an example Child Node:

#### Example Child Node Using a Node Pointer
 

The example Pointer above becomes a child of this node, visible in the [ MISSING LINK : 01a ]  or using the other tree views described in [Trees](#trees).

The advantages to Node Pointers are many, including:

- The tree represents a hierachy of actual content, rather than the files containing the content.

- The tree permits nesting both within and beyond file level.

- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.
### Duplicate Pointers  

Node Pointers may point more than once to the same node, so that content can be reused or referenced across multiple trees within the same project:

Here is the same example child node from above: 
### Recursive Node Pointers  

Recursive Node Pointers would be ones that point to one of their containing node's own ancestors, causing a circular reference.

These are not prohibited, but the recursion will not be drawn if it is already contained in the tree. Instead, the point of recursion will show RECURSION, with a link to the Node ID of the node causing the recursion.

For example, this Node Pointer points back to the root node of the table of contents: | Urtext Documentation >>a5m. Instead of the table of contents being drawn recursively from this node, you can see the recursion point in the table of contents.

Note, however, that if you view the entire tree with another node as root, one full iteration will still appear, with the point of recursion falling elsewhere in the tree. For instance, below is the table of contents with the node "Pointers" ([Pointers](#pointers)) as root. See Dynamic Nodes ([ MISSING LINK : e82 ] ) for more information on how to generate trees like this in dynamic nodes.
#### Example Recursive Node Tree
	Example Recursive Node Tree 
	Pointers >lmu
	├── Duplicate Pointers >00t
	│   └── Example Child Node Using a Node Pointer >001
	└── Recursive Node Pointers >6ct
	    ├── Urtext  Version: 0.2.0-alpha >a5m
	    │   ├── Quick Start and Guides >z7t
	    │   │   ├── Urtext Syntax Guide >znj
	    │   │   └── Urtext Action Guide >e1x
	    │   ├── About Urtext >013
	    │   │   ├── Description >yv2
	    │   │   ├── Comparison To Other Tools >h8z
	    │   │   ├── Uses >lhs
	    │   │   └── Project Requirements and Features >006
	    │   ├── Using this document >009
	    │   │   ├── With Sublime Text >e6m
	    │   │   └── Using Pythonista Urtext >lvf
	    │   ├── Setup >003
	    │   │   ├── Making a New Project >dce
	    │   │   │   └── Sublime >00a
	    │   │   ├── Using/Adding Existing Files >00b
	    │   │   │   ├── Sublime >rij
	    │   │   │   ├── Pythonista >ouh
	    │   │   │   └── Python >b44
	    │   │   ├── Using a Sublime Project >c3n
	    │   │   └── Sublime Text Interface Tips >000
	    │   │       ├── Syntax Highlighting >01d
	    │   │       ├── Hiding Tabs >015
	    │   │       ├── Hiding Line Numbers >01e
	    │   │       ├── Full Screen / Distraction Free Mode >002
	    │   │       ├── Disable Prompts for File Reload >023
	    │   │       └── Remove Indent Guides >1rc
	    │   ├── Nodes >01j
	    │   │   ├── Node Identity (Node IDs) >01h
	    │   │   ├── File Level Nodes >01g
	    │   │   │   └── Creating a File Level Node >ekz
	    │   │   │       ├── Sublime >xo8
	    │   │   │       ├── Pythonista >xcx
	    │   │   │       └── Python >83e
	    │   │   ├── Inline Nodes >004
	    │   │   │   ├── Example inline node >00e
	    │   │   │   ├── Creating Inline Nodes >rbs
	    │   │   │   │   ├── Sublime >8fh
	    │   │   │   │   ├── Pythonista >hrv
	    │   │   │   │   └── Python >fv2
	    │   │   │   └── Syntax Highlighting of Inline Nodes (Sublime) >koe
	    │   │   ├── Compact Nodes >kpz
	    │   │   │   ├── Example Compact Node >d7b
	    │   │   │   │   └── Example inline node within the compact node >9up
	    │   │   │   └── Sublime >qwn
	    │   │   │       └── Pythonista >0yn
	    │   │   ├── Generating a node ID manually >rfp
	    │   │   │   └── Sublime >7n6
	    │   │   ├── Node Metadata >00x
	    │   │   │   ├── Reserved Metadata Keys >011
	    │   │   │   │   ├── title (overrides the default title) >00y
	    │   │   │   │   ├── index >00z
	    │   │   │   │   └── flags >cwb
	    │   │   │   │       └── - exclude_from_tree >1e3
	    │   │   │   └── Timestamps >005
	    │   │   │       ├── Timeline View >00k
	    │   │   │       └── Time Zones >7w6
	    │   │   │           └── Timezone List >zh1
	    │   │   └── The Node List >01i
	    │   │       └── Opening the Node List >hl7
	    │   │           └── Sublime >p78
	    │   ├── Trees >00h
	    │   │   ├── From any given node >00f
	    │   │   └── From the root >00g
	    │   ├── Links and Pointers >00j
	    │   │   ├── Links >0y2
	    │   │   │   └── Sublime Text tools to help with linking >00m
	    │   │   ├── Dynamically Titled Links >4vu
	    │   │   ├── Opening Links >01w
	    │   │   │   ├── Sublime >osu
	    │   │   │   └── Pythonista >iy8
	    │   │   ├── Viewing Linked Relationships >00u
	    │   │   ├── Linking to outside resources >00q
	    │   │   │   ├── Web >00o
	    │   │   │   └── Files >00p
	    │   │   ├── ? (Missing Node): > !RECURSION 3:
	    │   │   └── Traverse Mode >00w
	    │   │       └── Word Wrap in Traverse Mode >xci
	    │   ├── Using Multiple Projects at a Time >ipy
	    │   │   ├── Project Naming (Identification) >tgp
	    │   │   └── Linking Between Projects >7lx
	    │   ├── Converting and Exporting >ezg
	    │   │   ├── Example : Urtext Documentation Exported in Markdown to a File >m9d
	    │   │   └── Example : Fragment Exported to HTML >baq
	    │   ├── Search >k67
	    │   │   └── Full Text Search >4p9
	    │   │       ├── Searching >mzj
	    │   │       │   ├── Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lowe >k8v
	    │   │       │   └── Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind the >q8j
	    │   │       └── Search Using Dynamic Nodes >uy4
	    │   ├── Filenames >01m
	    │   ├── Development >01o
	    │   │   └── Make Installation Easier >mh8
	    │   └── File History >prp
	    └── Example Recursive Node Tree >01n

## Traverse ModeTraverse Mode    

This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.
### Word Wrap in Traverse Mode 

Since Traverse Mode splits the window into two or more panes, it is suggested to set Word Wrap Column to "Auto" in Sublime Settings. This will cause the edited views to wrap correctly no matter the screen or window/pane size, as well as in Sublime's Distraction Free Mode.

Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.


# Using Multiple Projects at a Time

To use multiple projects at once, there is a project context manager. When you initially pass a path to Urtext, it looks recursively in all sub folders for additional projects. If it finds a compilable Urtext project in any one, it adds these to the context manager.  You can then freely switch among projects, either explicitly, or using links between the projects (described below). When switching projects, all Urtext's features, content and behavior, including links, compiling, and all functions linked to UI buttons, will operate in the context of the selected project. 

You can put all your Urtext projects into sub folders of a single path. Alternatively, you may put them anyplace in the file system and choose as your Urtext root a folder that encompasses them all. Compiling may take longer if Urtext has to search through many unused directories. 

Using Python, it is possible to only instantiate a single project, without the context manager. The current implementations in Sublime and Pythonista, however, use the context manager by default, even if you are only using a single project.

Recall that what defines a project is a folder. This is also what separates it from other projects. If you add other Urtext project folders into the initial path, they will all be accessible from the same project list.

To switch between projects in Sublime, select Urtext: Select Project from the command palette.
In Pythonista, use "Switch Projects" from the feature menu.
## Project Naming (Identification) 

Unlike nodes, projects are uniquely identified by name. For this reason, each project must have an unique name within the running instance of Urtext. Projects can be named using the project_title key in the project's project_settings node. If no name is present, the project's name becomes its absolute path in the file system.
## Linking Between Projects 

You may also link from one project to another within the text. To so this, use the following syntax:

{"name or path of the other project"}[ MISSING LINK : idj ] 
(This link is only an example and is non-functioning)

Following this link will change the project context to the named project and open its specified node.

# Converting and Exporting

Urtext can convert (export) nodes, and sets of nodes, to plaintext, Markdown and HTML. Results can be either output to a file or written back into another node within the same project. Like other dynamic functions, exporting is dynamic ; that is, when changes are made to the source nodes, exports are immediately updated, whether they are in a project node or an external file.

Exporting is not implemented in user-interface menus/buttons. Instead, export by utilizing dynamic definitions.

The export command has three components:

export : (format) : ( source_node_id )

(format) : One of `plaintext`, `markdown` or `html`
(source_id): The source node to export.
## Example : Urtext Documentation Exported in Markdown to a File  

The following dynamic definition exports this entire documentation (from its root node [Urtext  Version: 0.2.0-alpha](#urtext--version:-0.2.0-alpha) ) in Markdown format to a file called documentation.md:

ss
## Example : Fragment Exported to HTML  

The following Dynamic Definition exports the [Links and Pointers](#links-and-pointers) section of the documentation to HTML, into a node inside this one:

# Search
## Full Text Search   

Fuzzy and Full Text Search are already implemented in many modern desktop text editors and some mobile text editors. However Urtext has a built-in search and index capability to avoid reliance on editors and environments.
### Searching
#### Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lowe r edge of the screen. Dynamically search results will be shown in a scratch view as you enter search terms. Press ESC to cancel.  Results include links to source nodes.
#### Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind the  search field. To exit, tap outside the search field.
### Search Using Dynamic Nodes 	

Search results can populate a dynamic node by using the key-value pair:

- search:(string)

For example, the following definition targets node[Example Search Results](#example-search-results) (below) and populates it with all nodes containing the word "urtext".
#### Example Search Results
Example Search Results 
Opening Links[Opening Links](#opening-links)
Python[Python](#python)
Sublime Text Implementation Setup[Sublime Text Implementation Setup](#sublime-text-implementation-setup)
Metadata List[Metadata List](#metadata-list)
More About Node IDs[More About Node IDs](#more-about-node-ids)
Sublime[Sublime](#sublime)
Uses[Uses](#uses)
iPhone/iPad/iOS[iPhone/iPad/iOS](#iphone/ipad/ios)
Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
0.1.11-alpha[0.1.11-alpha](#0.1.11-alpha)
Filenames[Filenames](#filenames)
Description[Description](#description)
Node Identity (Node IDs)[Node Identity (Node IDs)](#node-identity-node-ids)
The Node List[The Node List](#the-node-list)
Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lowe[Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lowe](#sublime-:-select-`urtext:-search`-from-the-command-pallete.-this-provides-an-input-panel-on-the-lowe)
Project Naming (Identification)[Project Naming (Identification)](#project-naming-identification)
Pythonista[Pythonista](#pythonista)
Full Text Search[Full Text Search](#full-text-search)
Search Using Dynamic Nodes[Search Using Dynamic Nodes](#search-using-dynamic-nodes)
Disable Prompts for File Reload[Disable Prompts for File Reload](#disable-prompts-for-file-reload)
0.1.14-alpha[0.1.14-alpha](#0.1.14-alpha)
About Urtext[About Urtext](#about-urtext)
Download and Install Dependencies Manually[Download and Install Dependencies Manually](#download-and-install-dependencies-manually)
Quick Start and Guides[Quick Start and Guides](#quick-start-and-guides)
Example : Urtext Documentation Exported in Markdown to a File[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file)
Projects, Structure and Compiling[Projects, Structure and Compiling](#projects,-structure-and-compiling)
Using a Sublime Project[Using a Sublime Project](#using-a-sublime-project)
Urtext Syntax Guide[Urtext Syntax Guide](#urtext-syntax-guide)
Sublime[Sublime](#sublime)
Pythonista[Pythonista](#pythonista)
Python[Python](#python)
Sublime[Sublime](#sublime)
Python[Python](#python)
Make Installation Easier[Make Installation Easier](#make-installation-easier)
Dependencies and Installation (Sublime)[Dependencies and Installation (Sublime)](#dependencies-and-installation-sublime)
From the root[From the root](#from-the-root)
tag_all[tag_all](#tag_all)
With Sublime Text[With Sublime Text](#with-sublime-text)
Pythonista[Pythonista](#pythonista)
Using this document[Using this document](#using-this-document)
Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind the[Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind the](#pythonista-:-use-the-"?"-urtext-button.-results-will-be-updated-in-real-time-in-the-view-behind-the)
Setup[Setup](#setup)
Full Screen / Distraction Free Mode[Full Screen / Distraction Free Mode](#full-screen-/-distraction-free-mode)
Timestamps[Timestamps](#timestamps)
Inline Nodes[Inline Nodes](#inline-nodes)
Project Requirements and Features[Project Requirements and Features](#project-requirements-and-features)
Converting and Exporting[Converting and Exporting](#converting-and-exporting)
Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
Download Dependencies from a Monorepo[Download Dependencies from a Monorepo](#download-dependencies-from-a-monorepo)
Using Multiple Projects at a Time[Using Multiple Projects at a Time](#using-multiple-projects-at-a-time)
Python[Python](#python)
Python[Python](#python)
Timeline View[Timeline View](#timeline-view)
Sublime Text tools to help with linking[Sublime Text tools to help with linking](#sublime-text-tools-to-help-with-linking)
project_settings[project_settings](#project_settings)
Sublime[Sublime](#sublime)
Urtext  Version: 0.2.0-alpha[Urtext  Version: 0.2.0-alpha](#urtext--version:-0.2.0-alpha)
From any given node[From any given node](#from-any-given-node)
Node Metadata[Node Metadata](#node-metadata)
Syntax Highlighting of Inline Nodes (Sublime)[Syntax Highlighting of Inline Nodes (Sublime)](#syntax-highlighting-of-inline-nodes-sublime)
Pythonista Urtext Implementation Setup[Pythonista Urtext Implementation Setup](#pythonista-urtext-implementation-setup)
Using Pythonista Urtext[Using Pythonista Urtext](#using-pythonista-urtext)
File History[File History](#file-history)
Viewing Linked Relationships[Viewing Linked Relationships](#viewing-linked-relationships)
Traverse Mode[Traverse Mode](#traverse-mode)
Urtext Action Guide[Urtext Action Guide](#urtext-action-guide)

# Filenames


Since node identities are independent of their containing filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

<index> <title>.txt

If no index is present:

<node id> <title>.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.

# Development
## Make Installation Easier  

The way Sublime Text is currently set up, manually installing all the dependency modules is the easiest way to get it set up. Alternatives such as using git subtrees, wrapping each individual dependency in a separate Sublime Package and then making those Packages dependencies of the Urtext Package, etc., all end up involving both more maintenance and more legwork for the end user than just manually installing everything.

If any developer can suggest a better solution, please submit a pull request.

Here are some relevant links:

https://forum.sublimetext.com/t/dependencies-in-package-control-3/14646
https://packagecontrol.io/docs/dependencies

https://forum.sublimetext.com/t/how-to-add-python-modules-to-sublime-text-3/41558

There is a method described in this thread which has not been explored yet:
https://forum.sublimetext.com/t/dependencies-in-package-control-3/14646/5
Example:
https://github.com/packagecontrol/requests

# File History

Urtext files, being in plaintext, can be versioned using tools such as Git, Subversion, Mercurial, and others. Those tools are intended mainly for coding, when it is generally considered bad practice to commit non-working/non-compiling iterations of a project. Though Urtext files do compile, their actual text content is not a factor in this, so is reasonable to track changes at all stages of a project, even at granular levels.

Though use of powerful version control tools is not discouraged, Urtext has its own, lighter versioning system that tracks edits in the background at discrete intervals so it is not necessary to make explicit "commits" to have access to file history. Urtext creates a single, linear, nondestructive history of each file's content, with each snapshot being a "diff", or record of changes since the previous snapshot. When a previous state is restored, no "checkout" or "rewind" occurs; rather, the newly restored state is appended to the end of the history. Therefore, in addition to functioning as version control, the feature can also be used as a non-destructive "undo/redo" editing history that saves state after the file is closed.

The default interval is 10 seconds, and can be modified in project_settings. 
To access a file's timeline, use Control-Shift-G in Sublime Text. 

Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.



License: GNU General Public License 3.0
