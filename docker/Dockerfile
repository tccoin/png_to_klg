FROM nvidia/cudagl:11.4.2-devel-ubuntu20.04
LABEL org.opencontainers.image.authors="junzhewu@umich.edu"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends g++ cmake cmake-gui libboost-all-dev build-essential wget unzip
RUN apt-get update && apt-get install -y --no-install-recommends libopencv-dev

# RUN wget http://sourceforge.net/projects/opencvlibrary/files/opencv-unix/2.4.9/opencv-2.4.9.zip \
#     && unzip opencv-2.4.9.zip \
#     && cd opencv-2.4.9 \
#     && mkdir build \
#     && cd build \
#     && cmake -D BUILD_NEW_PYTHON_SUPPORT=OFF -D WITH_OPENCL=OFF -D WITH_OPENMP=ON -D INSTALL_C_EXAMPLES=OFF -D BUILD_DOCS=OFF -D BUILD_EXAMPLES=OFF -D WITH_QT=OFF -D WITH_OPENGL=OFF -D WITH_VTK=OFF -D BUILD_PERF_TESTS=OFF -D BUILD_TESTS=OFF -D WITH_CUDA=OFF -D BUILD_opencv_gpu=OFF .. \
#     && make -j8 \
#     && make install

RUN apt-get update && apt-get install -y --no-install-recommends python pip git
RUN pip install numpy
RUN git clone https://github.com/tccoin/png_to_klg.git  \
    && cd png_to_klg \
    && mkdir build \
    && cd build \
    && cmake .. \
    && make