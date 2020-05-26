FROM debian
ADD debian.list /etc/apt/sources.list.d/
RUN apt-get update && apt-get -y upgrade && apt -y install nginx && apt-get clean && \
    cd /var/www/ && rm -rf ./* && \
    mkdir -p OksanaIlnitskaya.com/img && \
    chmod -R 754 /var/www/OksanaIlnitskaya.com/ && \
    useradd Egor && groupadd Ilnitskaya && usermod -aG Oksana Ilnitskaya && \
    chown -R Egor:Batasov /var/www/OksanaIlnitskaya.com/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/OksanaIlnitskaya.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user Egor/g' /etc/nginx/nginx.conf
ADD index.html /var/www/OksanaIlnitskaya.com/
ADD img.jpg /var/www/OksanaIlnitskaya.com/img/
CMD ["nginx", "-g", "daemon off;"]
