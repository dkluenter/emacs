<!-- $Id:$ -->

# Minutes of MeetUp 26-02-2020

At the MeetUp session on Feb. 26.2020 some topics where discussed,
this are a few minutes that I can remember . :(

###  change of $EMACS_HOME and $XDG_CONF_HOME directories

   -'~/.emacs.d/' could be kept
   -'~/.config/emacs/' might be required if XDG interferes
   
   - themes integration, security problem?
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

   This lisp code is based on my old xemacs configuration from the
    late 90's


    (defun Init-kill-entire-line (&optional arg)
    "Kill the entire line.
    With prefix argument, kill that many lines from point.  Negative
    arguments kill lines backward.
    When calling from a program, nil means \"no arg\",
    a number counts as a prefix arg."
    (interactive "*P")
    (let ((kill-whole-line t))
    (beginning-of-line)
    (call-interactively 'kill-line)))
    
    (global-set-key [f8]
    `   (if (fboundp 'kill-entire-line)
        'kill-entire-line 'Init-kill-entire-line))
    
