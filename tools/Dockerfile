FROM ghcr.io/osgeo/gdal:ubuntu-small-latest
# docker image containing all tools in order to transform a GeoTIFF into a PNG terrain tileset

LABEL MAINTAINER thomas.halwax@syncpoint.io

ENV LANG=C.UTF-8
ENV LC_ALL=C.UTF-8
## install pip3/pipx and Mapbox's RasterIO (rio)
## install plugins for rio from https://github.com/mapbox/rasterio/wiki/Rio-plugin-registry
RUN apt-get -y update && apt-get install -y --fix-missing python3-pip pipx vim proj-bin \
    && pipx install rasterio \
    && pipx install rio-rgbify --include-deps \
    && pipx install rio-mbtiles --include-deps \
    && pipx install mbutil \
    && apt-get clean

## add pipx bin to path
ENV PATH="/root/.local/bin:$PATH"
