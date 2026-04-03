FROM docker.io/library/debian:bookworm-slim
LABEL \
    org.opencontainers.image.title="RKNN2 Lite Python Runtime" \
    org.opencontainers.image.description="A python environment with the RKNN2 Lite Runtime available"
RUN \
    apt-get update && \
    apt-get install -y python3.11 python3.11-venv curl wget && \
    apt-get clean && \
    curl -L# 'https://github.com/airockchip/rknn-toolkit2/raw/refs/heads/master/rknpu2/runtime/Linux/librknn_api/aarch64/librknnrt.so' -o /usr/lib/librknnrt.so &&\
    python3.11 -m venv /opt/rknn --upgrade-deps &&\
    /opt/rknn/bin/python3.11 -m pip install https://github.com/airockchip/rknn-toolkit2/raw/refs/heads/master/rknn-toolkit-lite2/packages/rknn_toolkit_lite2-2.3.2-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl &&\
    /opt/rknn/bin/python3.11 -m pip install opencv-python-headless &&\
    /opt/rknn/bin/python3.11 -m pip cache purge
ENV PATH="/opt/rknn/bin:$PATH"
