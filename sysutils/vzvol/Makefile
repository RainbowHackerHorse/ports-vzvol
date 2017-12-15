# $FreeBSD$

PORTNAME=					vzvol
DISTVERSION=				0.3.0
CATEGORIES=					sysutils
DSTVERSIONPREFIX=			v

MAINTAINER=					rainbow@purlinux.org
COMMENT=					vzvol is a tool to assist in the creation of ZFS zvols as storage for various virtualization providers

LICENSE=					BSD2CLAUSE
LICENSE_FILE=				${WRKSRC}/LICENSE

RUN_DEPENDS=

GROUPS=         			operator

USE_GITHUB=					yes
GH_ACCOUNT=					RainbowHackerHorse
GH_TAGNAME=					v0.3.0

IS_INTERACTIVE=				yes
NO_ARCH=					yes


WRKSRC=						${WRKDIR}/vzvol-${DISTVERSION}

OPTIONS_DEFINE+=			DOCS PROGRESS
OPTIONS_GROUP=				FILESYSTEMS
OPTIONS_GROUP_FILESYSTEMS= 	EXT XFS
OPTIONS_DEFAULT=			EXT XFS PROGRESS
EXT_RUN_DEPENDS=			e2fsprogs:sysutils/e2fsprogs
XFS_RUN_DEPENDS=			xfsprogs:sysutils/xfsprogs
PROGRESS_RUN_DEPENDS= 		pv:sysutils/pv
PROGRESS_DESC=				Enables progress bars for import
EXT_DESC=					Install support for ext2, ext3, and ext4
XFS_DESC=					Install support for XFS Filesystem

DOCSFILES=					README LICENSE
PORTDOCS=					${DOCSFILES}

.include <bsd.port.pre.mk>

# Still working on stuff here

.include <bsd.port.mk>
