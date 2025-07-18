# FROM ubuntu
FROM nvcr.io/nvidia/pytorch:24.05-py3
#191940200295.dkr.ecr.us-east-2.amazonaws.com/coder:nvidia_pytorch_24_05_py3
# FROM public.ecr.aws/q6e0p8s4/test-coder:nvidia_pytorch_24_05_p3
#FROM nvcr.io/nvidia/k8s/cuda-sample:vectoradd-cuda10.2

RUN apt-get update
RUN apt-get install vim sudo curl -y

RUN useradd -m -s /bin/bash -G sudo coder
USER coder

# Let's add a fancy prompt!
RUN echo "PS1='🐳 \[\033[1;36m\]\h \[\033[1;34m\]\W\[\033[0;35m\] \[\033[1;36m\]# \[\033[0m\]'" > ~/.bashrc