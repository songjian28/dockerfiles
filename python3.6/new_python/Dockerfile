FROM python:3.6.15-alpine

ADD build build
RUN cd build \
    && cp sgerrand.rsa.pub /etc/apk/keys/sgerrand.rsa.pub \
    && apk add --force-overwrite glibc-bin-2.35-r0.apk glibc-i18n-2.35-r0.apk glibc-2.35-r0.apk \
    && gunzip /usr/glibc-compat/share/i18n/charmaps/UTF-8.gz \
    # && /usr/glibc-compat/bin/localedef -i en_AG -f UTF-8 en_AG.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_AU -f UTF-8 en_AU.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_BW -f UTF-8 en_BW.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_CA -f UTF-8 en_CA.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_DK -f UTF-8 en_DK.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_GB -f UTF-8 en_GB.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_HK -f UTF-8 en_HK.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_IE -f UTF-8 en_IE.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_IN -f UTF-8 en_IN.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_NG -f UTF-8 en_NG.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_NZ -f UTF-8 en_NZ.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_PH -f UTF-8 en_PH.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_SG -f UTF-8 en_SG.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_US -f UTF-8 en_US.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_ZA -f UTF-8 en_ZA.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_ZM -f UTF-8 en_ZM.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i en_ZW -f UTF-8 en_ZW.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i zh_HK -f UTF-8 zh_HK.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i zh_SG -f UTF-8 zh_SG.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i zh_TW -f UTF-8 zh_TW.UTF-8 \
    # && /usr/glibc-compat/bin/localedef -i zu_ZA -f UTF-8 zu_ZA.UTF-8 \
    && /usr/glibc-compat/bin/localedef -i zh_CN -f UTF-8 zh_CN.UTF-8 \
    && cp Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    && apk del glibc-i18n \
    && cd / \
    && rm -rf build 
