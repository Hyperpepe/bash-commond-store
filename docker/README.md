docker容器操作

```sh
//挂载docker目录到宿主机目录下
docker run -v /home/AIresult:/app/Result -d <image_name>
//映射主机端口
docker run -p 55555:8888 -d imID

docker ps -a//查看所有容器（包括已停止的）
docker images//查看所有容器（包括已停止的）
docker stop ctID
docker save -o imID > im.tar
docker load -i im.tar 
docker commit <running_container_id> new_image_name


```

