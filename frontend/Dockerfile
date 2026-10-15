FROM nginx:1.24.0-alpine3.17-slim
RUN rm -rf /usr/share/nginx/html/* && \
    rm -rf /etc/nginx/nginx.conf && \
    rm -rf /etc/nginx/conf.d/default.conf

RUN chown -R nginx:nginx /var/cache/nginx /var/log/nginx /etc/nginx/conf.d && \
    touch /var/run/nginx.pid && \
    chown nginx:nginx /var/run/nginx.pid
COPY static/ /usr/share/nginx/html/
COPY nginx.conf /etc/nginx/
USER nginx




#RUN rm -rf /usr/share/nginx/html/*
#RUN rm -rf /etc/nginx/nginx.conf
#RUN rm -rf /etc/nginx/conf.d/default.conf
#COPY static/ /usr/share/nginx/html/
#COPY nginx.conf /etc/nginx/
