# $OpenBSD: Makefile,v 1.9 2020/05/14 17:26:44 semarie Exp $

MODPY_EGG_VERSION =	5.2.8
TRYTON_MODULE =		account

TRYTON_DEPENDS +=	party \
			currency \
			company

RUN_DEPENDS +=		devel/py-dateutil${MODPY_FLAVOR} \
			databases/py-sql${MODPY_FLAVOR} \
			devel/py-simpleeval${MODPY_FLAVOR}

.include <bsd.port.mk>
