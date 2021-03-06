# Created by: Lung-Pin Chang <changlp@cs.nctu.edu.tw>
# $FreeBSD$

PORTNAME=	django_compressor
PORTVERSION=	2.2
CATEGORIES=	www python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	ultima@FreeBSD.org
COMMENT=	Compresses linked and inline JavaScript/CSS into a single cached file

LICENSE=	MIT

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}versiontools>=1.8.2:devel/py-versiontools@${FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}django-appconf>=0.4:www/py-django-appconf@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}rcssmin>=0:archivers/py-rcssmin@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}rjsmin>=0:archivers/py-rjsmin@${FLAVOR}

USES=		python${PY_SLIMIT}
USE_PYTHON=	autoplist distutils
NO_ARCH=	yes

OPTIONS_DEFINE=		BEAUTIFULSOUP LXML HTML5LIB SLIMIT
BEAUTIFULSOUP_DESC=	Enable BeautifulSoupParser
LXML_DESC=		Enable LxmlParser
HTML5LIB_DESC=		Enable Html5LibParser
SLIMIT_DESC=		Enable SlimIt JavaScript filter

BEAUTIFULSOUP_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}beautifulsoup>=4:www/py-beautifulsoup@${FLAVOR}
LXML_RUN_DEPENDS=		${PYTHON_PKGNAMEPREFIX}lxml>0:devel/py-lxml@${FLAVOR}
HTML5LIB_RUN_DEPENDS=		${PYTHON_PKGNAMEPREFIX}html5lib>0:www/py-html5lib@${FLAVOR}
SLIMIT_RUN_DEPENDS=		${PYTHON_PKGNAMEPREFIX}slimit>=0.8.1:www/py-slimit@${FLAVOR}
SLIMIT_VARS=	PY_SLIMIT=:2.7

.include <bsd.port.mk>
