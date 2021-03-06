# Created by: netchild@FreeBSD.org
# $FreeBSD$

PORTNAME=	skype
PORTVERSION=	4.3.0.37
PORTREVISION=	5
PORTEPOCH=	1
CATEGORIES=	net-im
MASTER_SITES=	http://download.skype.com/linux/
PKGNAMESUFFIX=	4

MAINTAINER=	ports@FreeBSD.org
COMMENT=	P2P VoIP software

RUN_DEPENDS=	${LINUXBASE}/lib/skype_oss_wrapper/libpulse.so.0:audio/linux-skype_oss_wrapper

CONFLICTS=	skype-devel-[0-9]*

OPTIONS_DEFINE=	VIDEO
OPTIONS_DEFAULT=VIDEO

NO_BUILD=	yes

USES=		cpe desktop-file-utils linux tar:bzip2
USE_LINUX=	fontconfig xorglibs qt qt-x11 qtwebkit openssl pulseaudio-libs

RESTRICTED=	Redistribution prohibited.

SKYPEDIR=	share/skype
PORTDOCS=	LICENSE README
PLIST_SUB+=	SKYPEDIR=${SKYPEDIR}
SUB_FILES=	skype.sh
SUB_LIST+=	SKYPEDIR=${SKYPEDIR}

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MVIDEO}
RUN_DEPENDS+=	webcamd:multimedia/webcamd
USE_LINUX+=	libv4l
SUB_LIST+=	VIDEO="LD_PRELOAD=/usr/lib/libv4l/v4l2convert.so "
.else
SUB_LIST+=	VIDEO=""
.endif

do-install:
	@${INSTALL} -d ${STAGEDIR}${PREFIX}/share/applications
	@${INSTALL_DATA} ${WRKSRC}/skype.desktop \
	    ${STAGEDIR}${PREFIX}/share/applications/
	@${INSTALL_DATA} ${WRKSRC}/icons/SkypeBlue_48x48.png \
	    ${STAGEDIR}${PREFIX}/share/pixmaps/skype.png
	@cd ${WRKSRC}/ && ${MKDIR} ${STAGEDIR}${PREFIX}/${SKYPEDIR} && \
	    ${COPYTREE_SHARE} "avatars icons sounds lang" \
	        ${STAGEDIR}${PREFIX}/${SKYPEDIR}/

# The binary main program
	@${INSTALL_PROGRAM} ${WRKSRC}/skype ${STAGEDIR}${PREFIX}/${SKYPEDIR}/

# The wrapper for main program
	@${INSTALL_SCRIPT} ${WRKDIR}/skype.sh ${STAGEDIR}${PREFIX}/bin/skype

# Documentation
	@${INSTALL} -d ${STAGEDIR}${DOCSDIR}
	@cd ${WRKSRC} && ${INSTALL_DATA} ${PORTDOCS} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
