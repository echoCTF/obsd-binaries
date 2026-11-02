COMMENT =		memcached user defined functions for MariaDB/MySQL

GH_ACCOUNT =		echoCTF
GH_PROJECT =		memcached_functions_mysql
GH_COMMIT =		f6be465b522ce693a67a9d60f4df3fb1b7e58403
DISTNAME =		memcached_functions_mysql-1.1.20261102

CATEGORIES =		databases

HOMEPAGE =		https://github.com/echoCTF/memcached_functions_mysql

# GPLv2
PERMIT_PACKAGE =	Yes

WANTLIB =		c memcached pthread

BUILD_DEPENDS =		databases/mariadb,-main
LIB_DEPENDS =		devel/libmemcached

USE_GMAKE =		Yes
USE_LIBTOOL =		gnu

AUTOCONF_VERSION =	2.72
AUTOMAKE_VERSION =	1.17
CONFIGURE_STYLE =	autoreconf
CONFIGURE_ARGS =	--libdir=${PREFIX}/lib/mysql/plugin \
			--disable-static \
			--with-mysql=${LOCALBASE}/bin/mariadb_config \
			--with-libmemcached=${LOCALBASE}

# MariaDB loads UDFs by plain name (SONAME "libmemcached_functions_mysql.so")
MAKE_FLAGS =		libmemcached_functions_mysql_la_LDFLAGS="-module -avoid-version"

NO_TEST =		Yes

post-install:
	rm -f ${PREFIX}/lib/mysql/plugin/*.la
	${INSTALL_DATA_DIR} ${PREFIX}/share/memcached_functions_mysql
	${INSTALL_DATA} ${WRKSRC}/sql/*.sql ${WRKSRC}/utils/install.pl \
		${PREFIX}/share/memcached_functions_mysql/

.include <bsd.port.mk>
