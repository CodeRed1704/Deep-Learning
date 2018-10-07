# Deep-Learning

## Installing Tensorflow GPU for Ubuntu (TF - 1.8.0, CUDA - 9.0, CUDNN - 7.1.4)

``` 
Step - 1:
 Download deb file
https://developer.nvidia.com/cuda-90-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=debnetwork
 sudo dpkg -i cuda-repo-ubuntu1604-9-0-local_9.0.176-1_amd64.deb
Step - 2:
 sudo apt update
Step - 3:
 sudo apt install cuda-9.0
Step - 4: 
 Download cudnn 7.1.4 from nvidia website for cuda 9.0
 https://developer.nvidia.com/rdp/cudnn-archive
Step - 5:
  tar -xzvf cudnn-9.0-linux-x64-v7.tgz
  sudo cp cuda/include/cudnn.h /usr/local/cuda-9.0/include
  sudo cp cuda/lib64/libcudnn* /usr/local/cuda-9.0/lib64
  sudo ldconfig /usr/local/cuda/lib64
Step - 6:
  sudo chmod a+r /usr/local/cuda/lib64/libcudnn*
Step - 7:
  Append the following lines to "`/.bashrc"
    export LD_LIBRARY_PATH=/usr/lib/nvidia-396
    export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:$LD_LIBRARY_PATH
    export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
Step - 8:
  pip3 install tensorflow-gpu==1.8
Step - 9:
  python3 -c "import tensorflow as tf"
  (Should not print anything)


```
## Installing Tensorflow Model Server

sudo pip install tensorflow-serving-api

echo "deb [arch=amd64] http://storage.googleapis.com/tensorflow-serving-apt stable tensorflow-model-server tensorflow-model-server-universal" | sudo tee /etc/apt/sources.list.d/tensorflow-serving.list

curl https://storage.googleapis.com/tensorflow-serving-apt/tensorflow-serving.release.pub.gpg | sudo apt-key add -

sudo apt-get update && sudo apt-get install tensorflow-model-server
