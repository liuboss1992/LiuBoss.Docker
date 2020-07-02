# ==================================================================
# lcb-py36-cuda90
# maintrainer: Chuanbin Liu (774054270@qq.com)
# ------------------------------------------------------------------
# python        3.6    (apt)
# ==================================================================

FROM nvidia/cuda:9.2-cudnn7-devel-ubuntu16.04

ENV LD_LIBRARY_PATH=/usr/local/cuda/lib64:/lib/x86_64-linux-gnu:/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH PATH=/usr/local/cuda-9.2/bin:$PATH
ENV LC_ALL=C
ENV TZ=Asia/Shanghai


RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list
RUN APT_INSTALL="apt-get install -y --no-install-recommends"
RUN PIP_INSTALL="python -m pip --no-cache-dir install --upgrade -i https://pypi.tuna.tsinghua.edu.cn/simple " && \
    rm -rf /var/lib/apt/lists/* \
           /etc/apt/sources.list.d/cuda.list \
           /etc/apt/sources.list.d/nvidia-ml.list
RUN	apt-get update && apt-get install -y --no-install-recommends \
		build-essential \
		cmake \
		git \
		wget \
		libatlas-base-dev \
		libboost-all-dev \
		libgflags-dev \
		libgoogle-glog-dev \
		libhdf5-serial-dev \
		libleveldb-dev \
		liblmdb-dev \
		libopencv-dev \
		libprotobuf-dev \
		libsnappy-dev \
		protobuf-compiler \
		nano \
		libopenblas-dev \
		liblapack-dev \
		python-tk \
		openssh-client \
		openssh-server \
        autossh \
        expect && \
	apt-get install --no-install-recommends libboost-all-dev && \
	apt-get install libopenblas-dev \
		liblapack-dev \
		libatlas-base-dev \
		libgflags-dev \
		libgoogle-glog-dev \
		liblmdb-dev \
		gfortran && \
	apt-get install -y build-essential git \
		libprotobuf-dev \
		libleveldb-dev \
		libsnappy-dev \
		libopencv-dev \
		libboost-all-dev \
		libhdf5-serial-dev \
		libgflags-dev \
		libgoogle-glog-dev \
		liblmdb-dev \
		protobuf-compiler \
		protobuf-c-compiler \
		libyaml-dev \
		libffi-dev \
		libssl-dev \
		python-dev \
		python-pip \
		python3-pip \
		liblmdb-dev \
		time \
		vim \
		screen \
		tmux 

RUN apt-get install -y --no-install-recommends software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y --no-install-recommends python3.6 python3.6-dev && \
    wget -O ~/get-pip.py \
        https://bootstrap.pypa.io/get-pip.py && \
    python3.6 ~/get-pip.py && \
    ln -s /usr/bin/python3.6 /usr/local/bin/python3 && \
    ln -s /usr/bin/python3.6 /usr/local/bin/python && \
    $PIP_INSTALL \
        pip

RUN	mkdir ~/.pip && echo "[global]" > ~/.pip/pip.conf && \
	echo "index-url=https://pypi.tuna.tsinghua.edu.cn/simple" >> ~/.pip/pip.conf && \
	echo "format = columns" >> ~/.pip/pip.conf


RUN	ldconfig && \
	apt-get -y clean && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* ~/*

EXPOSE 6006

WORKDIR	/

