# $FreeBSD$

PORTNAME=		lisk-hub
DISTVERSION=	1.20.0-rc.1
CATEGORIES=		net-p2p
		
DIST_SUBDIR=	${PORTNAME}
EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX}

MAINTAINER=		gessadavide@gmail.com
COMMENT=		LiskHub Lisk Wallet

LICENSE=		APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

ONLY_FOR_ARCHS=	amd64

BUILD_DEPENDS=	electron:devel/electron4 \
				npm:www/npm-node10 \

USES=			desktop-file-utils

USE_GITHUB=		yes
GH_ACCOUNT=		LiskHQ
GH_TAGNAME=		v${DISTVERSION}

SOURCE_COMMIT_HASH=	c410ad21ef6c3f061077502afbe6d607dc2e9a09

ELECTRON_VER=	4.2.9
NODE_VER=		10.11.0

DATADIR=	${PREFIX}/share/lisk-hub
TMPDIR=		${WRKDIR}



do-build:
	cd ${WRKSRC} && \
		npm install && \
		npm run clean-build && \
		mkdir ./app/build && \
		npm run copy-files && \
		npm run build-prod && \
		npm run build-electron && \
		npm run pack 

do-install:


.include <bsd.port.mk>