FROM shadowsocks/shadowsocks-libev

EXPOSE 1080
CMD exec  ss-local \
    -s $SERVER_ADDR \
    -p $SERVER_PORT -k $PASSWORD \
    -m $METHOD -b 0.0.0.0 -l 1080
