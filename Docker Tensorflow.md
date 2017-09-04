# Docker_Tensorflow
## Docker command
* `docker ps -a` 查看所有镜像
* `exit` 退出当前容器
* `docker run -it -v /home/dock/Downloads:/usr/Downloads ubuntu64 /bin/bash` 挂载本地的目录 通过-v参数，冒号前为宿主机目录，必须为绝对路径，冒号后为镜像内挂载的路径
* `docker commit -a "runoob.com" -m "my apache" aa97726a4d85  gcr.io/tensorflow/tensorflow:latest-gpu-v3` 提交镜像
* `docker images` 查看镜像


## Docker Tensorflow的使用
* `nvidia-docker run -it gcr.io/tensorflow/tensorflow:latest-gpu bash` 启动tensorflow容器
* `nvidia-docker run -it -p 8888:8888 gcr.io/tensorflow/tensorflow:latest-gpu` 使用jupyter
* `nvidia-smi` 查看GPU使用情况


## Caveat
* windward@10.108.110.67 9018
* `docker`命令前要加`sudo`
* `/media/bnrc2/_backup/yangyi/models`
* `nvidia-docker run -it -p 8888:8888 -v /media/bnrc2/_backup/yangyi/models:/home/windward/models gcr.io/tensorflow/tensorflow:latest-gpu`
* `nvidia-docker run  -it -v /media/bnrc2/_backup/yangyi/:/home/windward/models  gcr.io/tensorflow/tensorflow:latest-gpu-v3 bash`
* `bazel-bin/im2txt/train \
  --input_file_pattern="/home/windward/models/models/im2txt/im2txt/data/mscoco/train-?????-of-00256" \
  --inception_checkpoint_file="/home/windward/models/models/im2txt/im2txt/data/inception_v3.ckpt" \
  --train_dir="/home/windward/models/models3/models/im2txt/im2txt/model/train" \
  --train_inception=false \
  --number_of_steps=1000000`



### 丁丁 server
* `sudo nvidia-docker run -it gcr.io/tensorflow/tensorflow:latest bash`
* `sudo docker commit -a "nvidia" -m "add vim" 6c29b9a827a9  gcr.io/tensorflow/tensorflow:latest`
* `sudo docker run -it -v /home/windward:/root gcr.io/tensorflow/tensorflow:latest bash`