# $FreeBSD$

PORTNAME=		lisk-core
DISTVERSION=	2.0.2
CATEGORIES=		net-p2p
DIST_SUBDIR=	${PORTNAME}
EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX}

USE_GITHUB=		yes
GH_ACCOUNT=		LiskHQ
SOURCE_COMMIT_HASH=	6cc8bd48a829f6985f51ee169c06e057f927c5ca
GH_TAGNAME=		v${DISTVERSION}

LICENSE=		APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

MAINTAINER=		gessadavide@gmail.com
COMMENT=		lisk-core node

OPTIONS_DEFINE= REDIS
OPTIONS_DEFAUL=	
REDIS_DESC=		Enable Redis cache
REDIS_BUILD_DEPENDS=       redis:databases/redis-server

ONLY_FOR_ARCHS=	amd64
NODE_VER=		10.15.3
BUILD_DEPENDS=	npm:www/npm-node10 \
				postgres:databases/postgresql10-server

do-build:
	cd ${WRKSRC} && \
		npm ci && \
		npm run build

.include <bsd.port.mk>
