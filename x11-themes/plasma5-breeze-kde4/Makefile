# $FreeBSD$

PORTNAME=	breeze
DISTVERSION=	${KDE_PLASMA_VERSION}
CATEGORIES=	x11-themes kde kde-plasma
PKGNAMESUFFIX=	-kde4

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Plasma5 Breeze visual style for KDE4

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

CMAKE_ON=	USE_KDE4

USES=		cmake:outsource compiler:c++11-lang cpe gettext \
		kde:4 pkgconfig tar:xz
USE_KDE=	kdelibs automoc4
USE_QT4=	corelib dbus gui svg \
		moc_build qmake_build rcc_build uic_build
USE_XORG=	x11 xcb

DISTINFO_FILE=	${.CURDIR}/../plasma5-breeze/distinfo

.include <bsd.port.mk>
