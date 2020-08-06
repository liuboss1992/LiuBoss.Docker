# ==================================================================
# lcb-py36-cuda90-torch041
# maintrainer: Chuanbin Liu (774054270@qq.com)
# base img: liuboss/pami:liucb-py36-cuda10-pycore
# ------------------------------------------------------------------
# python        3.6    (apt)
# torch		1.5.1
# other python add-on
# ==================================================================

FROM liuboss/pami:liucb-py36-cuda102-pycore


RUN pip --default-timeout=10000 install \
		tensorboard==2.3.0 \
		tensorboardX==2.1 \
		torch==1.5.1 torchvision==0.6.1 && \
    pip install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI' && \
    pip install git+https://github.com/cocodataset/panopticapi.git

ARG USER_ID=1082

RUN groupadd wheel && \
        useradd -m --no-log-init --system  --uid ${USER_ID} liucb -g sudo && \
        echo 'liucb ALL=(ALL) ALL' >> /etc/sudoers && \
        groupadd -g ${USER_ID} liucb && \
        usermod -aG wheel liucb && \
        sed -i '19s/# a/a/g' /etc/pam.d/su


RUN	ldconfig && \
	apt-get -y clean && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* ~/*

EXPOSE 6006

WORKDIR	/

