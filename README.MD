#Install nginx-rtmp module
    #Clone nginx-rtmp-module
    git clone https://github.com/sergey-dryabzhinsky/nginx-rtmp-module.git
    #Install nginx dependencies
    sudo apt-get install build-essential libpcre3 libpcre3-dev libssl-dev
    #Download nginx
    wget https://nginx.org/download/nginx-1.18.0.tar.gz

    tar -xf nginx-1.18.0.tar.gz

    cd nginx-1.18.0
    #Compile nginx
    ./configure --with-http_ssl_module --add-module=../nginx-rtmp-module
    # if error install zlib1g yet >
    sudo apt-get install zlib1g zlib1g-dev
    #end 
    make -j 1
    sudo make install

#Configuration file nginx.conf
    #create backup nginx.conf
    mv usr/local/nginx/conf/nginx.conf usr/local/nginx/conf/nginx.conf.original
    #fix nginx.conf
        #server1: nginx_server1.conf
        #server2: nginx_server2.conf
            #Set up directory path contain m3u8, ts file
            sudo su
            cd usr/local/nginx/conf/
            mkdir /nginx
            mkdir /nginx/hls
            cat /etc/passwd | grep nginx
            cat /etc/passwd
            chown -R www-data:www-data /nginx


#Streaming by OBS

#Show streamng video by VLC
server controller:101.75/121.128
server server:101.40
server edge:101.41