FROM httpd:2.4.59-bookworm

RUN echo "# 以下由patrick所加" >> /usr/local/apache2/conf/httpd.conf \
    && echo "LoadModule proxy_module modules/mod_proxy.so" >> /usr/local/apache2/conf/httpd.conf \
    && echo "LoadModule proxy_fcgi_module modules/mod_proxy_fcgi.so" >> /usr/local/apache2/conf/httpd.conf \
    && echo "Include /usr/local/apache2/conf/extra/private" >> /usr/local/apache2/conf/httpd.conf

