AUTOMAKE_OPTIONS = foreign subdir-objects

AM_CPPFLAGS=-Iinclude/ -Incs4pad/include -Incs4pad/include/pieces -Incs4pad/include/physics-animation

SUBDIRS = m4 etc include common engines controls ncs4pad desktop apps inner-res res

COMMON_BINS = mguxdemo activity-loader

if MGRM_PROCESSES
OTHER_BINS = mginit
else
OTHER_BINS =
endif

bin_PROGRAMS = $(COMMON_BINS) $(OTHER_BINS)

APP_LIBS = \
    engines/libengines.la \
    apps/libapps.la \
    desktop/libdesktop.la \
    common/libcommon.la \
    controls/libcontrols.la \
    ncs4pad/src/libncs4pad.la \
    inner-res/libinner-res.la

mguxdemo_SOURCES = main.cc
mguxdemo_LDADD = $(APP_LIBS) @DEP_LIBS@

activity_loader_SOURCES = test/apps/activity-loader.cc
activity_loader_LDADD = $(APP_LIBS) @DEP_LIBS@

mginit_SOURCES = mginit.c
mginit_LDADD = $(APP_LIBS) @DEP_LIBS@

EXTRA_DIST = LICENSE README.md MiniGUI.cfg MiniGUI.cfg.win32 \
    res tools

install-data-local:
	$(INSTALL_DATA) MiniGUI.cfg $(prefix)/bin/MiniGUI.cfg
	$(INSTALL_DATA) mgncs.cfg $(prefix)/bin/mgncs.cfg
	$(INSTALL_DATA) mgncs4touch.cfg $(prefix)/bin/mgncs4touch.cfg
