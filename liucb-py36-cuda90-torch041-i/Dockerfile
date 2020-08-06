# ==================================================================
# lcb-py36-cuda90-torch041
# maintrainer: Chuanbin Liu (774054270@qq.com)
# base img: liuboss/pami:liucb-py36-cuda90-pycore
# ------------------------------------------------------------------
# python        3.6    (apt)
# torch			0.4.1
# tensorflow	1.14.0
# other python add-on
# ==================================================================

FROM liuboss/pami:liucb-py36-cuda90-pycore


RUN pip --default-timeout=10000 install \
		tensorflow-gpu==1.14.0 \
		tensorboard==1.14.0 \
		tensorboardX==1.8 \
		torch==0.4.1 torchvision==0.2.1 

RUN	ldconfig && \
	apt-get -y clean && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* ~/*

ARG USER_ID=1082

RUN groupadd wheel && \
        useradd -m --no-log-init --system  --uid ${USER_ID} liucb -g sudo && \
        echo 'liucb ALL=(ALL) ALL' >> /etc/sudoers && \
        groupadd -g ${USER_ID} liucb && \
        usermod -aG wheel liucb && \
        sed -i '19s/# a/a/g' /etc/pam.d/su

EXPOSE 6006

WORKDIR	/

