# Makefile for program source directory in GNU NLS utilities package.
# Copyright (C) 1995, 1996, 1997 by Ulrich Drepper <drepper@gnu.ai.mit.edu>
# Copyright (C) 2004-2008 Rodney Dawes <dobey.pwns@gmail.com>
#
# This file may be copied and used freely without restrictions.  It may
# be used in projects which are not available under a GNU Public License,
# but which still want to provide support for the GNU gettext functionality.
#
# - Modified by Owen Taylor <otaylor@redhat.com> to use GETTEXT_PACKAGE
#   instead of PACKAGE and to look for po2tbl in ./ not in intl/
#
# - Modified by jacob berkman <jacob@ximian.com> to install
#   Makefile.in.in and po2tbl.sed.in for use with glib-gettextize
#
# - Modified by Rodney Dawes <dobey.pwns@gmail.com> for use with intltool
#
# We have the following line for use by intltoolize:
# INTLTOOL_MAKEFILE

GETTEXT_PACKAGE = blueman
PACKAGE = blueman
VERSION = 1.23

SHELL = /bin/bash

srcdir = .
top_srcdir = ..
top_builddir = ..


prefix = /usr/local
exec_prefix = ${prefix}
datadir = ${datarootdir}
datarootdir = ${prefix}/share
libdir = ${exec_prefix}/lib
DATADIRNAME = share
itlocaledir = $(prefix)/$(DATADIRNAME)/locale
subdir = po
install_sh = ${SHELL} /home/schramm/src/blueman-deb/blueman-1.23-git201403102151/install-sh
# Automake >= 1.8 provides $(MKDIR_P).
# Until it can be supposed, use the safe fallback:
mkdir_p = $(install_sh) -d

INSTALL = /usr/bin/install -c
INSTALL_DATA = ${INSTALL} -m 644

GMSGFMT = /usr/bin/msgfmt
MSGFMT = /usr/bin/msgfmt
XGETTEXT = /usr/bin/xgettext
INTLTOOL_UPDATE = /usr/bin/intltool-update
INTLTOOL_EXTRACT = /usr/bin/intltool-extract
MSGMERGE = INTLTOOL_EXTRACT="$(INTLTOOL_EXTRACT)" XGETTEXT="$(XGETTEXT)" srcdir=$(srcdir) $(INTLTOOL_UPDATE) --gettext-package $(GETTEXT_PACKAGE) --dist
GENPOT   = INTLTOOL_EXTRACT="$(INTLTOOL_EXTRACT)" XGETTEXT="$(XGETTEXT)" srcdir=$(srcdir) $(INTLTOOL_UPDATE) --gettext-package $(GETTEXT_PACKAGE) --pot

ALL_LINGUAS = 

PO_LINGUAS=$(shell if test -r $(srcdir)/LINGUAS; then grep -v "^\#" $(srcdir)/LINGUAS; else echo "$(ALL_LINGUAS)"; fi)

USER_LINGUAS=$(shell if test -n "$(LINGUAS)"; then LLINGUAS="$(LINGUAS)"; ALINGUAS="$(ALL_LINGUAS)"; for lang in $$LLINGUAS; do if test -n "`grep \^$$lang$$ $(srcdir)/LINGUAS 2>/dev/null`" -o -n "`echo $$ALINGUAS|tr ' ' '\n'|grep \^$$lang$$`"; then printf "$$lang "; fi; done; fi)

USE_LINGUAS=$(shell if test -n "$(USER_LINGUAS)" -o -n "$(LINGUAS)"; then LLINGUAS="$(USER_LINGUAS)"; else if test -n "$(PO_LINGUAS)"; then LLINGUAS="$(PO_LINGUAS)"; else LLINGUAS="$(ALL_LINGUAS)"; fi; fi; for lang in $$LLINGUAS; do printf "$$lang "; done)

POFILES=$(shell LINGUAS="$(PO_LINGUAS)"; for lang in $$LINGUAS; do printf "$$lang.po "; done)

DISTFILES = Makefile.in.in POTFILES.in $(POFILES)
EXTRA_DISTFILES = ChangeLog POTFILES.skip Makevars LINGUAS

POTFILES = \
	../data/ui/adapters-tab.ui \
	../data/ui/adapters.ui \
	../data/ui/applet-passkey.ui \
	../data/ui/manager-main.ui \
	../data/ui/services.ui \
	../data/ui/services-network.ui \
	../data/ui/services-transfer.ui \
	../data/ui/services-audio.ui \
	../data/ui/send-dialog.ui \
	../data/ui/assistant.ui \
	../data/ui/device-list-widget.ui \
	../data/ui/applet-plugins-widget.ui \
	../data/ui/gsm-settings.ui \
	../data/ui/net-usage.ui \
	../blueman/Lib.py \
	../blueman/main/KillSwitchNG.py \
	../blueman/main/NetConf.py \
	../blueman/main/HalManager.py \
	../blueman/main/PulseAudioUtils.py \
	../blueman/main/SignalTracker.py \
	../blueman/main/Device.py \
	../blueman/main/KillSwitch.py \
	../blueman/main/Mechanism.py \
	../blueman/main/PPPConnection.py \
	../blueman/main/FakeDevice.py \
	../blueman/main/Config.py \
	../blueman/main/__init__.py \
	../blueman/main/AppletService.py \
	../blueman/main/DhcpClient.py \
	../blueman/main/SpeedCalc.py \
	../blueman/main/BluezConfig.py \
	../blueman/main/applet/__init__.py \
	../blueman/main/applet/Transfer.py \
	../blueman/main/applet/BluezAgent.py \
	../blueman/main/PluginManager.py \
	../blueman/main/DbusService.py \
	../blueman/Functions.py \
	../blueman/gui/manager/ManagerMenu.py \
	../blueman/gui/manager/ManagerDeviceList.py \
	../blueman/gui/manager/ManagerDeviceMenu.py \
	../blueman/gui/manager/ManagerProgressbar.py \
	../blueman/gui/manager/ManagerStats.py \
	../blueman/gui/manager/ManagerToolbar.py \
	../blueman/gui/manager/__init__.py \
	../blueman/gui/GtkAnimation.py \
	../blueman/gui/DeviceSelectorDialog.py \
	../blueman/gui/CellRendererPixbufTable.py \
	../blueman/gui/PixbufTable.py \
	../blueman/gui/MessageArea.py \
	../blueman/gui/Animation.py \
	../blueman/gui/DeviceSelectorList.py \
	../blueman/gui/CommonUi.py \
	../blueman/gui/__init__.py \
	../blueman/gui/GsmSettings.py \
	../blueman/gui/DeviceList.py \
	../blueman/gui/GenericList.py \
	../blueman/gui/applet/__init__.py \
	../blueman/gui/applet/PluginDialog.py \
	../blueman/gui/Notification.py \
	../blueman/gui/DeviceSelectorWidget.py \
	../blueman/ods/OdsManager.py \
	../blueman/ods/OdsServerSession.py \
	../blueman/ods/OdsServer.py \
	../blueman/ods/__init__.py \
	../blueman/ods/OdsSession.py \
	../blueman/ods/OdsBase.py \
	../blueman/DeviceClass.py \
	../blueman/__init__.py \
	../blueman/Sdp.py \
	../blueman/Constants.py.in \
	../blueman/bluez/Adapter.py \
	../blueman/bluez/errors.py \
	../blueman/bluez/BlueZInterface.py \
	../blueman/bluez/utils.py \
	../blueman/bluez/Device.py \
	../blueman/bluez/ServiceInterface.py \
	../blueman/bluez/BaseInterface.py \
	../blueman/bluez/Manager.py \
	../blueman/bluez/__init__.py \
	../blueman/bluez/Agent.py \
	../blueman/plugins/config/Gconf.py \
	../blueman/plugins/config/__init__.py \
	../blueman/plugins/config/File.py \
	../blueman/plugins/mechanism/Hal.py \
	../blueman/plugins/mechanism/RfKill.py \
	../blueman/plugins/mechanism/Network.py \
	../blueman/plugins/mechanism/Ppp.py \
	../blueman/plugins/mechanism/Config.py \
	../blueman/plugins/mechanism/__init__.py \
	../blueman/plugins/manager/PulseAudioProfile.py \
	../blueman/plugins/manager/__init__.py \
	../blueman/plugins/manager/Services.py \
	../blueman/plugins/ConfigurablePlugin.py \
	../blueman/plugins/ManagerPlugin.py \
	../blueman/plugins/BasePlugin.py \
	../blueman/plugins/ServicePlugin.py \
	../blueman/plugins/ConfigPlugin.py \
	../blueman/plugins/AppletPlugin.py \
	../blueman/plugins/__init__.py \
	../blueman/plugins/applet/NetUsage.py \
	../blueman/plugins/applet/StatusIcon.py \
	../blueman/plugins/applet/Networking.py \
	../blueman/plugins/applet/NMDUNSupport.py \
	../blueman/plugins/applet/RecentConns.py \
	../blueman/plugins/applet/NMPANSupport.py \
	../blueman/plugins/applet/DBusService.py \
	../blueman/plugins/applet/NMMonitor.py \
	../blueman/plugins/applet/TransferService.py \
	../blueman/plugins/applet/KillSwitch.py \
	../blueman/plugins/applet/StandardItems.py \
	../blueman/plugins/applet/AuthAgent.py \
	../blueman/plugins/applet/__init__.py \
	../blueman/plugins/applet/PulseAudio.py \
	../blueman/plugins/applet/ExitItem.py \
	../blueman/plugins/applet/DhcpClient.py \
	../blueman/plugins/applet/NMIntegration.py \
	../blueman/plugins/applet/ShowConnected.py \
	../blueman/plugins/applet/AppIndicator.py \
	../blueman/plugins/applet/Headset.py \
	../blueman/plugins/applet/DiscvManager.py \
	../blueman/plugins/applet/Menu.py \
	../blueman/plugins/applet/PPPSupport.py \
	../blueman/plugins/applet/SerialManager.py \
	../blueman/plugins/applet/PowerManager.py \
	../blueman/plugins/MechanismPlugin.py \
	../blueman/plugins/services/Network.py \
	../blueman/plugins/services/__init__.py \
	../blueman/plugins/services/Audio.py \
	../blueman/plugins/services/Transfer.py \
	../blueman/iniparse/config.py \
	../blueman/iniparse/compat.py \
	../blueman/iniparse/ini.py \
	../blueman/iniparse/__init__.py \
	../data/blueman.desktop.in \
	../data/blueman-manager.desktop.in \
	../data/configs/org.blueman.policy.in \
	../apps/blueman-manager \
	../apps/blueman-services \
	../apps/blueman-applet \
	../apps/blueman-adapters \
	../apps/blueman-sendto \
	../apps/blueman-assistant \
	../apps/blueman-browse

CATALOGS=$(shell LINGUAS="$(USE_LINGUAS)"; for lang in $$LINGUAS; do printf "$$lang.gmo "; done)

.SUFFIXES:
.SUFFIXES: .po .pox .gmo .mo .msg .cat

AM_DEFAULT_VERBOSITY = 1
INTLTOOL_V_MSGFMT = $(INTLTOOL__v_MSGFMT_$(V))
INTLTOOL__v_MSGFMT_= $(INTLTOOL__v_MSGFMT_$(AM_DEFAULT_VERBOSITY))
INTLTOOL__v_MSGFMT_0 = @echo "  MSGFMT" $@;

.po.pox:
	$(MAKE) $(GETTEXT_PACKAGE).pot
	$(MSGMERGE) $< $(GETTEXT_PACKAGE).pot -o $*.pox

.po.mo:
	$(INTLTOOL_V_MSGFMT)$(MSGFMT) -o $@ $<

.po.gmo:
	$(INTLTOOL_V_MSGFMT)file=`echo $* | sed 's,.*/,,'`.gmo \
	  && rm -f $$file && $(GMSGFMT) -o $$file $<

.po.cat:
	sed -f ../intl/po2msg.sed < $< > $*.msg \
	  && rm -f $@ && gencat $@ $*.msg


all: all-yes

all-yes: $(CATALOGS)
all-no:

$(GETTEXT_PACKAGE).pot: $(POTFILES)
	$(GENPOT)

install: install-data
install-data: install-data-yes
install-data-no: all
install-data-yes: all
	linguas="$(USE_LINGUAS)"; \
	for lang in $$linguas; do \
	  dir=$(DESTDIR)$(itlocaledir)/$$lang/LC_MESSAGES; \
	  $(mkdir_p) $$dir; \
	  if test -r $$lang.gmo; then \
	    $(INSTALL_DATA) $$lang.gmo $$dir/$(GETTEXT_PACKAGE).mo; \
	    echo "installing $$lang.gmo as $$dir/$(GETTEXT_PACKAGE).mo"; \
	  else \
	    $(INSTALL_DATA) $(srcdir)/$$lang.gmo $$dir/$(GETTEXT_PACKAGE).mo; \
	    echo "installing $(srcdir)/$$lang.gmo as" \
		 "$$dir/$(GETTEXT_PACKAGE).mo"; \
	  fi; \
	  if test -r $$lang.gmo.m; then \
	    $(INSTALL_DATA) $$lang.gmo.m $$dir/$(GETTEXT_PACKAGE).mo.m; \
	    echo "installing $$lang.gmo.m as $$dir/$(GETTEXT_PACKAGE).mo.m"; \
	  else \
	    if test -r $(srcdir)/$$lang.gmo.m ; then \
	      $(INSTALL_DATA) $(srcdir)/$$lang.gmo.m \
		$$dir/$(GETTEXT_PACKAGE).mo.m; \
	      echo "installing $(srcdir)/$$lang.gmo.m as" \
		   "$$dir/$(GETTEXT_PACKAGE).mo.m"; \
	    else \
	      true; \
	    fi; \
	  fi; \
	done

# Empty stubs to satisfy archaic automake needs
dvi info ctags tags CTAGS TAGS ID:

# Define this as empty until I found a useful application.
install-exec installcheck:

uninstall:
	linguas="$(USE_LINGUAS)"; \
	for lang in $$linguas; do \
	  rm -f $(DESTDIR)$(itlocaledir)/$$lang/LC_MESSAGES/$(GETTEXT_PACKAGE).mo; \
	  rm -f $(DESTDIR)$(itlocaledir)/$$lang/LC_MESSAGES/$(GETTEXT_PACKAGE).mo.m; \
	done

check: all $(GETTEXT_PACKAGE).pot
	rm -f missing notexist
	srcdir=$(srcdir) $(INTLTOOL_UPDATE) -m
	if [ -r missing -o -r notexist ]; then \
	  exit 1; \
	fi

mostlyclean:
	rm -f *.pox $(GETTEXT_PACKAGE).pot *.old.po cat-id-tbl.tmp
	rm -f .intltool-merge-cache

clean: mostlyclean

distclean: clean
	rm -f Makefile Makefile.in POTFILES stamp-it
	rm -f *.mo *.msg *.cat *.cat.m *.gmo

maintainer-clean: distclean
	@echo "This command is intended for maintainers to use;"
	@echo "it deletes files that may require special tools to rebuild."
	rm -f Makefile.in.in

distdir = ../$(PACKAGE)-$(VERSION)/$(subdir)
dist distdir: $(DISTFILES)
	dists="$(DISTFILES)"; \
	extra_dists="$(EXTRA_DISTFILES)"; \
	for file in $$extra_dists; do \
	  test -f $(srcdir)/$$file && dists="$$dists $(srcdir)/$$file"; \
	done; \
	for file in $$dists; do \
	  test -f $$file || file="$(srcdir)/$$file"; \
	  ln $$file $(distdir) 2> /dev/null \
	    || cp -p $$file $(distdir); \
	done

update-po: Makefile
	$(MAKE) $(GETTEXT_PACKAGE).pot
	tmpdir=`pwd`; \
	linguas="$(USE_LINGUAS)"; \
	for lang in $$linguas; do \
	  echo "$$lang:"; \
	  result="`$(MSGMERGE) -o $$tmpdir/$$lang.new.po $$lang`"; \
	  if $$result; then \
	    if cmp $(srcdir)/$$lang.po $$tmpdir/$$lang.new.po >/dev/null 2>&1; then \
	      rm -f $$tmpdir/$$lang.new.po; \
            else \
	      if mv -f $$tmpdir/$$lang.new.po $$lang.po; then \
	        :; \
	      else \
	        echo "msgmerge for $$lang.po failed: cannot move $$tmpdir/$$lang.new.po to $$lang.po" 1>&2; \
	        rm -f $$tmpdir/$$lang.new.po; \
	        exit 1; \
	      fi; \
	    fi; \
	  else \
	    echo "msgmerge for $$lang.gmo failed!"; \
	    rm -f $$tmpdir/$$lang.new.po; \
	  fi; \
	done

Makefile POTFILES: stamp-it
	@if test ! -f $@; then \
	  rm -f stamp-it; \
	  $(MAKE) stamp-it; \
	fi

stamp-it: Makefile.in.in $(top_builddir)/config.status POTFILES.in
	cd $(top_builddir) \
	  && CONFIG_FILES=$(subdir)/Makefile.in CONFIG_HEADERS= CONFIG_LINKS= \
	       $(SHELL) ./config.status

# Tell versions [3.59,3.63) of GNU make not to export all variables.
# Otherwise a system limit (for SysV at least) may be exceeded.
.NOEXPORT:
