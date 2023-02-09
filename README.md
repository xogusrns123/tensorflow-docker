# tensorflow-docker
gpu랑 tensorflow 함께 사용하려니 환경 세팅이 귀찮아서 docker를 이용하려고 한다.
2023.02.09

# Installed Environment
설치 당시 환경
Docker Version: 20.10.12
OS/Arch: linux - Ubuntu 18.04.6 LTS
GPU: Nvidia Geforce RTX 1080 Ti
Nvidia-driver: 515.43.04 

# Installation Guide
먼저 Nvidia-docker를 설치해야한다.
나 격리된 컨테이너에서 GPU를 사용하는 AI/ML/DL 관련 작업을 하려고 하면 nvidia-smi 를 터미널에서 입력해도 GPU 자원을 사용할 수 없기 때문에 작업을 진행 할 수 없다. 이를 해결 해 줄 수 있는 것이 Nvidia-docker다. 설치를 후 조금의 옵션을 추가하면 자신의 컨테이너에서 GPU를 사용할 수 있다.
add nividia-docker github
```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
&& curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
&& curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
```
install nvidia-container-toolkit
```
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
```
restart docker service
```
sudo systemctl restart docker
```
