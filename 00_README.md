Hello! And welcome to your local (dev) vault.  The current file is located in
```
/Users/johnycsh/Dropbox/local_dev_vault
You can think of this somewhat similar to <DOCROOT> in Apache etc
```
(and no, that directory path will not somehow magically update)

I'm having trouble keeping track of what gets stored (or referenced where). Partially this is probably because I am old and my working memory fits on an index card. But also,  most people dont usually care how/where there files live anymore. 

To illustrate where obsidian/excalidraw lay things down on the file system, lets take a screenshot of the current layout:
![[Pasted image 20230118173133.png]]
Of course, as soon as that screenshot was pasted into the current document, it had to be saved somehwere:
![[Pasted image 20230118173106.png]]
![[Pasted image 20230118172511.png]]
As you can see. By default, Obsidian will generate a new filename using the scheme shown above (Pasted||image|timedatestamp|.png) By default these are stored in what i will be referring to as VAULT_ROOT.

**Not** shown above: By default, Obsidian will create a hidden  directory in the top level of every "Vault" it imports/opens. We'll dig into those shortly.
![[obsidian_dot_dir.png]]


The eager (damaged?) among you may have wondered 'But Johnny, what *exactly* happend when you cut/paste that buffer into Obsidian.app?'' Or, to put the emphasis on the actual concern 'But Johnny, it seems like the act of cut-and-paste **must** be creating some sort of **state**. And if that state isnt tracked (and then sync'd, etc), how can you be sure things wont somehow get lost or corrupt across devices?

Excellent question! Let's examine this is some detail.

All obsidian does is accept the paste buffer, *generate a unique filename/location* for the buffer, write it do disk (./Pasted image 20230118173106.png), and then __auto insert__ a quick reference to it by placing the cursor after a ![[your_file_here]].  In fact, if you reference over that link right there, obsidian will inform you that the referenced file does not exist, and prompt you to create it. Just like a wiki would.

These shallow (simple?) REF-Links illustrate why Obsidian.app *requires* the concept of a **vault**' in the first place. Since Obsidian does __not__ have any out-of-band state tracking mechanism, these relatively simple quick-links must be paired with a 'vault'. 

The 'vault' serves as the equivalent of an Apache DocumentRoot.

Right?



