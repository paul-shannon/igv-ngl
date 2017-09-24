build: webpack assemble buildPackage installPackage

assemble:
	(cd ./dist; m4 -P igvNgl.html-template | sed s/\`//g > igvNgl.html)
	ls -l ./dist/igvNgl.html

buildPackage:
	(cd ../../..; R CMD build --no-build-vignettes igv-ngl)

installPackage:
	(cd ../../..; R CMD INSTALL `ls -at igvNgl_* | head -1`)

webpack:
	npm update
	webpack

test:
	(cd ./dist; pwd)

all: clean install run

clean:
	- rm -rf dist/
	- rm -rf node_modules

install:
	npm install
