# Created by: Alex Dupre <ale@FreeBSD.org>
# $FreeBSD$

PORTNAME=	mpfr
PORTVERSION=	4.0.1
CATEGORIES=	math devel
MASTER_SITES=	http://www.mpfr.org/mpfr-current/ \
		GNU
DIST_SUBDIR=	${DISTNAME}

PATCH_SITES=	${MASTER_SITES}
PATCH_DIST_STRIP=	-p1

MAINTAINER=	ale@FreeBSD.org
COMMENT=	Library for multiple-precision floating-point computations

LICENSE=	LGPL3+
LICENSE_FILE=	${WRKSRC}/COPYING.LESSER

#PATCH_DEPENDS=	gpatch:devel/patch
LIB_DEPENDS=	libgmp.so:math/gmp

#PATCHLEVEL=	2
#PATCHFILES!=	/usr/bin/jot -s " " -w patch%02d ${PATCHLEVEL} 1 ${PATCHLEVEL}
#PATCH=		${LOCALBASE}/bin/gpatch

USES=		libtool tar:xz
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-gmp=${LOCALBASE}
INSTALL_TARGET=	install-strip
TEST_TARGET=	check
USE_LDCONFIG=	yes

INFO=		mpfr

PORTDOCS=	*

.include <bsd.port.mk>
