<!-- $Id: 25-03-2020.md,v 1.1 2020/02/28 14:23:20 dieter Exp dieter $ -->

# Minutes of MeetUp 26-02-2020

At the MeetUp session on Feb. 26.2020  

###  change of $EMACS_HOME and $XDG_CONF_HOME directories
   -'~/.emacs.d/' could be kept
   -'~/.config/emacs/' might be required if XDG interferes
   
   - themes integration
   - '(require 'cl)' is obsolete, should be '(require 'cl-lib) 
  
###  Markdown-Mode
          *A few lines frome my init.el*


    ((autoload 'markdown-mode "markdown-mode" 
    "Major mode for editing Markdown files" t)

    (autoload 'pandoc-mode "Minor Mode for Markdown" t)
    (add-to-list 'auto-mode-alist '("\\.md\\'" . markdown-mode))`
    
    (add-hook 'markdown-mode-hook 'pandoc-load-default-settings)
    (add-hook 'pandoc-mode-hook 'pandoc-load-default-settings)
    
    
With regard to *pandoc*, install a binary which 'markdown-mode'
will require in order to compile files.
Markdown produces restructured text, while Pandoc transforms restructured
text to printable format like PDF and HTML.

   [Pandoc] (https://pandoc.org/MANUAL.html)


### Kill entire Line


