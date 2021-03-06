# $OpenBSD: Makefile,v 1.23 2020/02/22 05:38:04 rsadowski Exp $

COMMENT =	extra KDE plasmoids
DISTNAME =	kdeplasma-addons-${MODKDE4_VERSION}
REVISION =	12

SHARED_LIBS =	lancelot-datamodels		51.1 # 1.7
SHARED_LIBS +=	lancelot			51.1 # 1.9
SHARED_LIBS +=	plasma_groupingcontainment	51.1 # 4.7
SHARED_LIBS +=	plasmacomicprovidercore		51.1 # 1.0
SHARED_LIBS +=	plasmapotdprovidercore		51.1 # 1.0
SHARED_LIBS +=	plasmaweather			51.1 # 4.7
SHARED_LIBS +=	rtm				51.1 # 4.7

WANTLIB =  c m pthread
WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += ICE SM X11 Xext Xrender Xtst
WANTLIB += lib/qt4/QtDBus lib/qt4/QtDeclarative lib/qt4/QtGui
WANTLIB += lib/qt4/QtNetwork lib/qt4/QtScript lib/qt4/QtSvg
WANTLIB += lib/qt4/QtWebKit lib/qt4/QtXml
WANTLIB += ${KDE4LIB}/akonadi-contact ${KDE4LIB}/akonadi-kde
WANTLIB += ${KDE4LIB}/kabc ${KDE4LIB}/kcalcore
WANTLIB += ${KDE4LIB}/kcmutils ${KDE4LIB}/kdeclarative ${KDE4LIB}/kdeui
WANTLIB += ${KDE4LIB}/kdewebkit ${KDE4LIB}/kemoticons ${KDE4LIB}/kexiv2
WANTLIB += ${KDE4LIB}/kidletime ${KDE4LIB}/kio
WANTLIB += ${KDE4LIB}/kfile ${KDE4LIB}/kmime ${KDE4LIB}/knewstuff3
WANTLIB += ${KDE4LIB}/kparts ${KDE4LIB}/kpimutils ${KDE4LIB}/kprintutils
WANTLIB += ${KDE4LIB}/kresources
WANTLIB += ${KDE4LIB}/krosscore ${KDE4LIB}/kunitconversion ${KDE4LIB}/kutils
WANTLIB += ${KDE4LIB}/kworkspace  ${KDE4LIB}/nepomuk
WANTLIB += ${KDE4LIB}/nepomukutils ${KDE4LIB}/plasma
WANTLIB += ${KDE4LIB}/plasmaclock ${KDE4LIB}/solid
WANTLIB += ${KDE4LIB}/taskmanager
WANTLIB += ${KDE4LIB}/threadweaver ${KDE4LIB}/weather_ion
WANTLIB += gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 gthread-2.0 ibus-1.0
WANTLIB += intl scim-1.0
WANTLIB += attica cln dbusmenu-qt qalculate qca qimageblitz qjson qoauth
WANTLIB += soprano xml2

MODULES =	multimedia/phonon

MODKDE4_USE =	pim workspace

RUN_DEPENDS =	misc/shared-mime-info \
		x11/gtk+3,-guic

LIB_DEPENDS =	devel/qjson \
		graphics/qimageblitz \
		inputmethods/ibus \
		inputmethods/scim \
		math/libqalculate \
		productivity/attica \
		security/qca \
		security/qoauth \
		x11/dbusmenu-qt \
		${MODKDE4_DEP_DIR}/libkexiv2>=${MODKDE4_DEP_VERSION}

CONFIGURE_ARGS =	-DCMAKE_DISABLE_FIND_PACKAGE_Eigen2=ON \
			-DCMAKE_DISABLE_FIND_PACKAGE_Qwt=ON

.include <bsd.port.mk>
