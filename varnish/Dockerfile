FROM newsdev/varnish:4.1.0

# Install Querystring Varnish module
ENV QUERYSTRING_VERSION=0.3
RUN \
  cd /usr/local/src/ && \
  curl -sfL https://github.com/Dridi/libvmod-querystring/archive/v$QUERYSTRING_VERSION.tar.gz -o libvmod-querystring-$QUERYSTRING_VERSION.tar.gz && \
  tar -xzf libvmod-querystring-$QUERYSTRING_VERSION.tar.gz && \
  cd libvmod-querystring-$QUERYSTRING_VERSION && \
  ./autogen.sh && \
  ./configure VARNISHSRC=/usr/local/src/varnish-$VARNISH_VERSION && \
  make install && \
  rm -r ../libvmod-querystring-$QUERYSTRING_VERSION*
