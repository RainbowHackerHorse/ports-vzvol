# $FreeBSD$

PORTNAME=					vzvol
DISTVERSIONPREFIX=			v
DISTVERSION=				0.5.4
CATEGORIES=					sysutils

MAINTAINER=					rainbow@purlinux.org
COMMENT=					Feature rich zvol manager

LICENSE=					BSD2CLAUSE
LICENSE_FILE=				${WRKSRC}/LICENSE

GROUPS=						operator

USE_GITHUB=					yes
GH_ACCOUNT=					RainbowHackerHorse
GH_TAGNAME=					v0.5.4

NO_ARCH=					yes

WRKSRC=						${WRKDIR}/vzvol-${DISTVERSION}

OPTIONS_DEFINE+=			DOCS PROGRESS VIRTUALBOX
OPTIONS_GROUP=				FILESYSTEMS
OPTIONS_GROUP_FILESYSTEMS=	EXT XFS
OPTIONS_DEFAULT=			EXT XFS PROGRESS VIRTUALBOX
EXT_RUN_DEPENDS=			e2fsprogs:sysutils/e2fsprogs
XFS_RUN_DEPENDS=			xfsprogs:sysutils/xfsprogs
PROGRESS_RUN_DEPENDS=		pv:sysutils/pv
VIRTUALBOX_RUN_DEPENDS=		virtualbox-ose:emulators/virtualbox-ose
PROGRESS_DESC=				Enables progress bars for import
EXT_DESC=					Install support for ext2, ext3, and ext4
XFS_DESC=					Install support for XFS Filesystem
VIRTUALBOX_DESC=			Support .VMDK creation with VirtualBox tools

DOCSFILES=					README LICENSE
PORTDOCS=					${DOCSFILES}

pre-install:
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/vzvol
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/vzvol/lib
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/vzvol/lib/shared
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/vzvol/lib/freebsd
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/vzvol/lib/linux

do-install:
	(cp ${WRKSRC}/bin/vzvol ${STAGEDIR}${PREFIX}/bin)
	(chmod +x ${STAGEDIR}${PREFIX}/bin/vzvol)
	(cd ${WRKSRC}/lib/ && ${COPYTREE_SHARE} . ${STAGEDIR}${PREFIX}/lib/vzvol/lib/)

.include <bsd.port.mk>
