# $OpenBSD: Makefile,v 1.34 2020/03/19 18:44:55 kn Exp $

COMMENT=		libgit2 bindings in Python

DISTNAME=		pygit2-${MODPY_EGG_VERSION}
PKGNAME=		${MODPY_PY_PREFIX}git2-${MODPY_EGG_VERSION}
REVISION =		1

MODULES=		lang/python
MODPY_EGG_VERSION=	1.0.1
MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes
MODPY_VERSION=		${MODPY_DEFAULT_VERSION_3}

WANTLIB += 		git2 pthread ${MODPY_WANTLIB}

DEBUG_PACKAGES =	${BUILD_PACKAGES}
LIB_DEPENDS=		devel/libgit2/libgit2>=0.28.0
BUILD_DEPENDS=		${RUN_DEPENDS}
RUN_DEPENDS=		devel/py-cffi${MODPY_FLAVOR} \
			devel/py-six${MODPY_FLAVOR}

.include <bsd.port.mk>
