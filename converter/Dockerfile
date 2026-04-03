ARG BASE_IMG=ghcr.io/laikulo/rknn2-toolkit:latest

FROM ${BASE_IMG}

LABEL \
    org.opencontainers.image.title="RKNN2 Toolkit Converter" \
    org.opencontainers.image.description="Tools for converting models into RKNN2 format"

ADD mkrknn rknn_convert /usr/local/bin
