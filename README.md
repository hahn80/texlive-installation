# texlive-installation

Options to install texlive from console.

1. Download texlive installer from [TeXLive](https://tug.org/texlive/acquire-netinstall.html)
2.  Create folder `Profiles/texlive/texmf-hanh`
3.  Run the installer command:
	```sh
	./install-tl --profile=texlive.profile
	```
4. Add TeXLive to system path.
5. Install additional packages when needed.
6. When backing up, just add path and run the update:
	```sh
	mktexlsr
	updmap-sys --nohash
	fmtutil-sys --no-error-if-no-engine=luametatex,luajithbtex,luajittex,mfluajit --no-strict --all
	```
7. Init user texmf tree:
	`tlmgr init-usertree`
	
8. More packages for user:

- Fonts:
	```
	tlmgr --user-mode install avantgar bookman charter courier helvetic mathpazo palatino times utopia vntex
	```

- Beamer:
	```
	tlmgr --user-mode install beamer tocbibind booktabs sectsty tocloft caption subfig translator
	```

- Jupyter:
	```
	tlmgr --user-mode install pdfcol adjustbox tcolorbox collectbox ucs environ enumitem wrapfig capt-of parskip float upquote eurosym fontspec unicode-math fancyvrb titling jknapltx lm-math
	```
	
- Math Font Open Types:
	```
	tlmgr --user-mode install xcharter xcharter-math stix2-otf
	```

- Missing type 1 for European Computer Modern Fonts: (Error: tcrm1200)
	```
	tlmgr --user-mode install cm-super
	```

*Notice*: `tlpdbopt_autobackup 0 -- disable backing up tl databases.`
Install perl-lib: `sudo apt install libfile-copy-recursive-perl`
