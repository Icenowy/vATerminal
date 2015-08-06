## Process this file with automake to produce Makefile.in

## Created by Anjuta


AM_CPPFLAGS = \
	-DPACKAGE_LOCALE_DIR=\""$(localedir)"\" \
	-DPACKAGE_SRC_DIR=\""$(srcdir)"\" \
	-DPACKAGE_DATA_DIR=\""$(pkgdatadir)"\" \
	$(VATERMINAL_CFLAGS)

AM_CFLAGS =\
	 -Wall\
	 -g

bin_PROGRAMS = vaterminal

vaterminal_SOURCES = \
	vaterminal.vala config.vapi vaterminal.gresource.xml

nodist_vaterminal_SOURCES = \
	resources.c

vaterminal_VALAFLAGS =  --pkg=vte-2.91  \
	--pkg=gtk+-3.0 \
	--pkg=posix \
	--gresources=$(srcdir)/vaterminal.gresource.xml

vaterminal_LDFLAGS = \
	-Wl,--export-dynamic

vaterminal_LDADD = $(VATERMINAL_LIBS)

resources.c: vaterminal.gresource.xml Makefile $(shell $(GLIB_COMPILE_RESOURCES) --generate-dependencies --sourcedir $(srcdir) $(srcdir)/vaterminal.gresource.xml)
	$(AM_V_GEN) XMLLINT=$(XMLLINT) $(GLIB_COMPILE_RESOURCES) --target $@ --sourcedir $(srcdir) --generate --c-name app $<

CLEANFILES = \
        vaterminal.c \
        resources.c

# Remove ui directory on uninstall
uninstall-local:
	-rm -r $(uidir)
	-rm -r $(pkgdatadir)

