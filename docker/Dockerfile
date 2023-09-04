FROM almalinux:8

# Install EPEL repository and then httpd, mod_perl, and perl
RUN dnf -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm && \
    dnf -y update && \
    dnf -y install httpd mod_perl perl perl-core && \
    dnf clean all

# Copy over the CGI configuration for Apache
COPY perl_cgi.conf /etc/httpd/conf.d/

EXPOSE 80

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
