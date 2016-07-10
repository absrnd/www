www.absrnd.com
===

source for www.absrnd.com static site which is created using Emacs org-mode.

The following code is defined in the .emacs file and then M-x org-publish-project
is used to convert the org files into html (in the public_html directory).

```
(require 'ox-publish)
;; setup absrnd projects
(setq org-publish-project-alist
      '(("org-absrnd"
	 :base-directory "~/projects/www.absrnd.com/org/"
	 :base-extension "org"
	 :publishing-directory "~/projects/www.absrnd.com/public_html/"
	 :recursive t
	 :publishing-function org-html-publish-to-html
	 :headline-levels 4             ; Just the default for this project.
	 :auto-preamble t)
	("media-absrnd"
	 :base-directory "~/projects/www.absrnd.com/org/"
	 :base-extension "css\\|js\\|png\\|jpg\\|gif\\|pdf\\|mp3\\|ogg\\|swf"
	 :publishing-directory "~/projects/www.absrnd.com/public_html/"
	 :recursive t
	 :publishing-function org-publish-attachment
	 )
	("absrnd" :components ("org-absrnd" "media-absrnd"))))
```

