# Exalted Character Sheet
A customizable LaTeX character sheet for fans of Exalted 3rd ed.

## What it is, and how you use it
This project is written for use by players and storytellers using the Exalted 3rd ed. game rules from Onyx Path. No technical background or prior experience with LaTeX or similar software is assumed, though for those of you who aren't used to working with computer code and markup documents, the learning curve may be a little steep.

I have made an effort to include clear and detailed directions to ease this for non-technical users. In particular, the template document included for generating your own printed characters has extensive comments that will guide you through filling it out. At a minimum, you'll need to be able to handle filling out some fields in a source docuement, and operating a compiler. I can't remove these steps for you unfortunately, but I would if I could! Those of you with some prior experience in LaTeX will probably find this section of the readme too introductory.

So, a brief guide to the topic of LaTeX and document compilation: LaTeX is a compiled markup language designed for type-setting. For those of you with some exposure to website design, you can think of it a lot like HTML for printers. For those of you who don't, it's a kind of *descriptive* language that you use to *instruct* a piece of software, in this case a LaTeX compiler, how to draw the document you want.

LaTeX files are computer code, and so are unavoidably ugly to read. All LaTeX files in this repository are named with a `.tex` at the end. There are a few rules of thumb to know while looking through them:
- Most LaTeX commands that control formatting, page layout, and other visual elements, or create objects like embedded images or horizontal rules, start with a backslash, followed by a command name, and one or more parameters enclosed in curly braces. "`\e`", "`\vspace`", and "`\usepackage{margin=0.5in}{geometry}`" are some examples.
- Human-readable notes can be included between lines of LaTeX code as a comment. Any text on a line that appears after a percent sign (`%`) is considered a comment, and is completely ignored by the compiler. There are lots of notes for you to read in these latex files, they're there to help.
- As in HTML documents, LaTeX documents have a header section and a body. The header section is where metadata goes. This stuff is important, but doesn't directly produce output on the page. In these LaTeX documents, the header is used to include packages, and create lots of custom macros. The header section comes first, and shouldn't be modified at all unless you know what you're doing. If you're uncertain, the comments in the document will help identify where the header starts and stops. The body is where the sheet's actual contents are described, and it's where your changes hsould happen. The body starts after the `\begin{document}` tag.

A lot of the ugly specifics of the LaTeX language have been wrapped up inside cleaner custom macros that are intended to be easy to work with. These macros are defined in the header, but you don't need to know how they work. For an exalted player, the name of the macro should give you an idea of what that macro will draw on your page. In most cases, you can look at the examples in the codument to get a pretty good idea of how to use them. If that's not enough, there's a big section of comments at the very bottom of the template document that gives a little more info on all the custom macros.

Control of things like multiple-column layouts is done with commands such as `\begin{multicols}{3}` (which starts a section of the sheet with three columns). I don't expect you to need to modify these commands at all, but you can play with them if you like. Be warned that you might break stuff if you're not a LaTeX master, so if you're going to do this, make sure you have a backup copy. Have fun experimenting, it's OK to break things as long as you don't lose anything important.

Before I get into the details of how to set up and use a compiler, let's talk for a moment about when and what to compile. Keeping in mind that compilation is the process of going from a description of your document, to the document itself, there are two ways I imagine people might use this character sheet document:
- To produce a blank "hand-fill" sheet that's suitable for batch printing ahead of time, and then filling in with pencil. Think of the blank character sheet at the back of the core book in most RPG systems.
- To produce a "preformatted", filled-out sheet containing the stats of a specific character. Think of the printed pre-generated characters you find in published adventures for some RPGs.

If you're planning to use "hand-fill" sheets, I've already compiled a blanked template, and included the resulting PDF in this repository (`ex3_blank.pdf`). Take a look and see if you like it, and if so, you can skip mucking with LaTeX and doing compilation alltogether. Just use this PDF. If you don't like my blank, that's fine, you can modify the LaTeX source for the blank and recompile it to produce a new, customized hand-fill sheet.

If you like the look of the "preformatted" characters (see `ex3_example_character.pdf`), the template is built to make it easy to make incremental changes to your character, such as adding a dot to a skill, or adding a new charm, and recompiling the document. This pretty much requires that you have a compiling solution that you're comfortable with, as you'll be using it frequently. If you need paper sheets you'll also be printing a lot, but this might be fine. If you don't need paper sheets it's a great way to have a pretty, formatted digital sheet that is easily distributable and easy to save and back up. I just keep my character on my laptop in most games, if this works for your group it can be a good strategy. If this is the way you plan to go, I recommend taking advantage of the power of digital formats to do things like back up your character. You can also use comments to keep track of stuff like XP earned and spent, without having it print out on your character every time.

The next section talks about what you need to make use of a LaTeX file after you've modified it, it's pretty important if you've never compiled a document before.

### LaTeX compilers.

Remember above where I said that LaTeX is a *descriptive* set of *instructions*? Once you've modified the template, you're not done. You need to take your file, which is essentially a blueprint, and hand it to a piece of software that can build the document you've described. This software is called a compiler, and so as you'd expect, the process is called compilation.

Using your compiler of choice will involve invoking the compiler and telling it the name of the document to compile. It will also need the image file for the logo (see the entry for `ex3_logo.jpg` below under "What each file is for") in order to render the page correctly. This process will be different for each compiler so I won't describe it here, but it's generally pretty simple and usually only involves one or two steps. There's lots of help online for this, try googling if you get stuck.

There are numerous options for installing a LaTeX compiler on your computer. I don't want to write a complete guide to setting up a LaTeX compiler, in large part because there are already lots of good guides online. I'll link some below for you to read. If you can't install the software locally, or don't want to, you can also use an online compiler (where you submit your document to a website, and get back the compiled result that they've built for you). The options for this are not wonderful unfortunately, but I'll list them below anyway.

To set up a local compiler, get TeXLive (a reputable and robust compiler) here: <http://tug.org/texlive/>
> you'll need the usage documentation [http://tug.org/texlive/doc.html](here). If you're on Windows and you want to use TeXLive you'll need the additional information on installing on Windows [http://tug.org/texlive/windows.html](here), or use the more popular [https://miktex.org/](MiKTeX). For Mac users, the TexLive people recommend using [http://tug.org/mactex/](MacTex) instead. Sorry for my Linux usage bias, I'm trying to write useful documentation, I swear!


To compile online, you can use the nice polished, fully-featured site [https://www.sharelatex.com/](ShareLaTeX), which has good support but you will need a paid subscription to use (you might consider sharing one among your group if logs of people want to make preformatted characters), or if you're cheapskates like me you could fight with the LaTeX compiler applet at [http://sciencesoft.at/latex/](ScienceSoft). Unfortunately, ScienceSoft compiles pure LaTeX and the template in this project uses pdfLaTeX, which is an extended version of the full language, so making this work will require some modification of the template macros, and is probably out of scope for a non-technical user (unless you have lots of time and determination, and like mucking with code and formatting).

If you're just doing a one-time modification (such as a change to the blank hand-fill sheet), and you email and ask nicely, I (the project maintainer) might be wiling to compile your document for you and email you the PDF output. No promises, especially if you've done something "extra creative" and caused some kind of layout issue I can't easily debug ;)

A final note: All the formatting packages used in this template should be distributed in TeXLive, but I have seen cases where one or more are missing where they were expected to be present. If you get an error about a package not being found (this error will look something like `! LaTeX Error: File `wrapfig.sty' not found.`), you can install the package manually. You can find the packages by name (take off the `.sty` in the above error) by searching [https://www.ctan.org/](CTAN), and install it with help from your chosen compiler's documentation (unless if you're using an online compiler, in which case complain to the maintainer).

### Contacting the maintainer.
Please refer to the contact info associated with my GitHub account. You will find it in the left-side panel on my GitHub root page, at <https://github.com/mongolsamurai>.

## What each file is for
`ex3_template.tex` is the template file that is intended for people who want to plug their character into a file to be printed in a nice formatted style. "Preformatted" characters should be created using this template.

`ex3_blank.tex` is a template modified to include hand-fillable blank fields. This document isn't intended to be modified, it is here for you to print in bulk so players can fill them out in pencil at the table. It *can* be modified if you don't like the formatting. Also see the next entry.

`ex3_blank.pdf` is the compiled output of the `.tex` file fo the same name. If you want a hand-fillable paper sheet, take a look at this and if you like it just use this file. There's no need to modify or compile the `.tex` unless you want to change the page layout, add additional fields or columns, etc.

`ex3_example_character.pdf` is an example of a printed pre-formatted character sheet created using the template. It's a reflavored solar that was used for an "abyssal" game in which I played, don't let the flavor fool you, it's using the solar template provided here without any custom abyssal modifications. This file is included here as an example of what a preformatted character looks like, in case you want to make your own.

`ex3_logo.jpg` is an Exalted 3 logo which is embedded in the sheet's header. If you're compiling a sheet (whether a modified blank for hand-filling, or a preformatted character) you need this file to be present in your working directory with this name. If you want to get creative, you can swap it out with another `.jpg` image with the same dimensions (for example with a custom design for your campaign or play group), but it the replacement must have the same name.

For the time being, only Solar character sheets are presented here. This is because as of this writing, no other splat books have been released. In the future, expect sheets for different exalt types to be divided into subdirectories.

## Property Disclaimer
Exalted, the Exalted 3rd ed. logo, and all associated material that appears in this document are property of White Wolf, Inc. The author  makes no claims of ownership or rights to any content used, referred to, or related to in this project.

The works produced in this repository are provided free of charge or property claims to anyone who finds them useful or convenient. Please use them, modify them, or redistribute them as you see fit. Any improvements or expansions suitable for general use will be eagerly considered for inclusion in this repository if submitted in a usable way to the maintainer.

