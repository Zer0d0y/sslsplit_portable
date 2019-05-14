# Ubuntu 16.04 | Debian 8.x

apt -y install libevent-dev libnet1-dev libssl-dev libpcap-dev

先确认依赖关系，

ldd sslsplit 

然后，复制文件到对应目录，切记不要覆盖已有文件。

# cp libssl.so.1.0.0 /usr/lib/x86_64-linux-gnu/libssl.so.1.0.0
# cp libcrypto.so.1.0.0 /usr/lib/x86_64-linux-gnu/libcrypto.so.1.0.0
cp libevent-2.0.so.5 /usr/lib/x86_64-linux-gnu/libevent-2.0.so.5
cp libevent_openssl-2.0.so.5 /usr/lib/x86_64-linux-gnu/libevent_openssl-2.0.so.5
cp libevent_pthreads-2.0.so.5 /usr/lib/x86_64-linux-gnu/libevent_pthreads-2.0.so.5
# cp libnet.so.1 /usr/lib/x86_64-linux-gnu/libnet.so.1
# cp libpcap.so.0.8 /usr/lib/x86_64-linux-gnu/libpcap.so.0.8
cp libevent_core-2.0.so.5 /usr/lib/x86_64-linux-gnu/libevent_core-2.0.so.5
# cp libpthread.so.0 /lib/x86_64-linux-gnu/libpthread.so.0
# cp libc.so.6 /lib/x86_64-linux-gnu/libc.so.6
# cp libdl.so.2 /lib/x86_64-linux-gnu/libdl.so.2
# cp ld-linux-x86-64.so.2 /lib64/ld-linux-x86-64.so.2

