all: ../ServerPack.xml

.PHONY: ../ServerPack.xml

MODS=$(sort $(wildcard *.mod.xml))

version:
	echo 0 > version

../ServerPack.xml: Makefile header footer version $(MODS)
	x=$$(cat version); echo $$(( $$x + 1 )) > version
	sed -e "s/%VERSION%/$$(cat version)/" header > $@
	for file in $(MODS); do cat $$file >> $@; done
	cat footer >> $@
