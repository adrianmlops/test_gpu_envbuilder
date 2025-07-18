# FROM ubuntu
FROM nvcr.io/nvidia/pytorch:24.05-py3
#191940200295.dkr.ecr.us-east-2.amazonaws.com/coder:nvidia_pytorch_24_05_py3
# FROM public.ecr.aws/q6e0p8s4/test-coder:nvidia_pytorch_24_05_p3
#FROM nvcr.io/nvidia/k8s/cuda-sample:vectoradd-cuda10.2

USER root
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    bash \
    wget \
    ca-certificates \
    curl \
    git \
    jq \
    locales \
    sudo \
    && rm -rf /var/lib/apt/lists/*

# Generate the desired locale (en_US.UTF-8)
RUN locale-gen en_US.UTF-8

# Make typing unicode characters in the terminal work.
ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8

# Remove the `ubuntu` user and add a user `coder` so that you're not developing as the `root` user
RUN userdel -r ubuntu && \
    useradd coder \
    --create-home \
    --shell=/bin/bash \
    --uid=1000 \
    --user-group && \
    echo "coder ALL=(ALL) NOPASSWD:ALL" >>/etc/sudoers.d/nopasswd

USER coder

# Let's add a fancy prompt!
RUN echo "PS1='🐳 \[\033[1;36m\]\h \[\033[1;34m\]\W\[\033[0;35m\] \[\033[1;36m\]# \[\033[0m\]'" > ~/.bashrc