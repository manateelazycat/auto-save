# What is auto-save ?
* Automatically save file content
* No annoying temporary files need to be cleaned
* No need to save manually, protect your fingers.

## Installation
Clone or download this repository (path of the folder is the `<path-to-auto-save>` used below).

In your `~/.emacs`, add the following three lines:
```Elisp
(add-to-list 'load-path "<path-to-auto-save>") ; add auto-save to your load-path
(require 'auto-save)
(auto-save-enable)

(setq auto-save-silent t)   ; quietly save
(setq auto-save-delete-trailing-whitespace t)  ; automatically delete spaces at the end of the line when saving

;;; custom predicates if you don't want auto save.
;;; disable auto save mode when current filetype is an gpg file.
(setq auto-save-disable-predicates
      '((lambda ()
      (string-suffix-p
      "gpg"
      (file-name-extension (buffer-name)) t))))
```
