# $OpenBSD: Makefile,v 1.41 2020/05/28 09:32:25 ajacoutot Exp $

COMMENT=		secure secret storage

GH_TAGNAME=		v1.4.2
GH_ACCOUNT=		hashicorp
GH_PROJECT=		vault

### Vault UI
# unversioned DISTFILE
DIST_SUBDIR=		vault-${GH_TAGNAME}
MODGO_FLAGS +=		-tags=ui
MASTER_SITES0=		https://distfiles.tristero.se/
EXTRACT_ONLY=		${DISTNAME}${EXTRACT_SUFX}
DISTFILES=		${DISTNAME}${EXTRACT_SUFX} \
			vault-${GH_TAGNAME:S/v//}-bindata_assetfs.go:0

CATEGORIES=		security net

HOMEPAGE=		https://www.vaultproject.io/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# MPLv2
PERMIT_PACKAGE=		Yes

WANTLIB += c pthread

MODULES=		lang/go

# go/src/github.com/hashicorp/vault/version/version.go
MODGO_LDFLAGS +=	-X github.com/hashicorp/vault/version.GitDescribe=${GH_TAGNAME:S/v//}
MODGO_LDFLAGS +=	-X github.com/hashicorp/vault/version.VersionPrerelease="" # empty

post-extract:
	install -m644 ${FULLDISTDIR}/vault-${GH_TAGNAME:S/v//}-bindata_assetfs.go \
		${WRKDIST}/http/bindata_assetfs.go

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/vault
	${INSTALL_DATA} ${FILESDIR}/vault.hcl \
		${PREFIX}/share/examples/vault

.include <bsd.port.mk>
