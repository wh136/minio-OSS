# minio-OSS
    https://docs.min.io/cn/minio-erasure-code-quickstart-guide.html
    docker run -p 9000:9000 minio/minio server /data
    /data数据卷用于存储配置和应用数据，启动时在容器的文件系统中创建，不过所有的数据都会在容器退出时丢失
    docker run -p 9000:9000 --name minio1 \
    -v /mnt/data:/data \
    -v /mnt/config:/root/.minio \
    minio/minio server /data
    
    Nginx 设置允许跨域
    add_header 'Access-Control-Allow-Origin' $http_origin;
		add_header 'Access-Control-Allow-Credentials' 'true';
		add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS';
		add_header 'Access-Control-Allow-Headers' 'DNT,web-token,app-token,Authorization,Accept,Origin,Keep-Alive,User-Agent,X-Mx-ReqToken,X-Data-Type,X-Auth-Token,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Range';
		add_header 'Access-Control-Expose-Headers' 'Content-Length,Content-Range';
