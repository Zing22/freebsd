# $FreeBSD$

PROG=	ktutil
MAN=	ktutil.8

SRCS=	add.c \
	change.c \
	copy.c \
	destroy.c \
	get.c \
	ktutil.c \
	ktutil-commands.c \
	ktutil-commands.h \
	list.c \
	purge.c \
	remove.c \
	rename.c

CFLAGS+=-I${KRB5DIR}/lib/roken -I${KRB5DIR}/lib/sl -I.
LIBADD=	kadm5clnt krb5 roken crypto edit sl vers

.include <bsd.prog.mk>

ktutil-commands.h: ${KRB5DIR}/admin/ktutil-commands.in
	${SLC} ${.ALLSRC:M*.in}

.for ext in c o
ktutil-commands.${ext}: ktutil-commands.h
.endfor

.PATH: ${KRB5DIR}/admin
