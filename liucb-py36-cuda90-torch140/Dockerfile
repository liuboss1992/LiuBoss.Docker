# ==================================================================
# lcb-py36-cuda90-torch041
# maintrainer: Chuanbin Liu (774054270@qq.com)
# base img: liuboss/pami:liucb-py36-cuda90-pycore
# ------------------------------------------------------------------
# python    3.6    (apt)
# torch		1.4.0
# other python add-on
# ==================================================================

FROM liuboss/pami:liucb-py36-cuda90-pycore


RUN pip --default-timeout=10000 install \
		tensorboardX==1.8 \
		torch==1.4.0 torchvision==0.5.0 

RUN	ldconfig && \
	apt-get -y clean && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* ~/*

EXPOSE 6006

WORKDIR	/

