COMMENT =		MariaDB Connector/C client library

GH_ACCOUNT =		mariadb-corporation
GH_PROJECT =		mariadb-connector-c
GH_TAGNAME =		v3.4.11

SHARED_LIBS =		mariadb 3.0

CATEGORIES =		databases

HOMEPAGE =		https://mariadb.com/kb/en/mariadb-connector-c/

PERMIT_PACKAGE =	Yes

WANTLIB =		c crypto pthread ssl

MODULES =		devel/cmake

MODCMAKE_POLICY_VERSION_OVERRIDE =	Yes

CONFIGURE_ARGS =	-DCMAKE_INSTALL_PREFIX="${PREFIX}" \
			-DCMAKE_C_FLAGS="-Wall"

NO_TEST =		Yes

.include <bsd.port.mk>
