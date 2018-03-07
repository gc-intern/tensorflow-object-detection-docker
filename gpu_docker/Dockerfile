FROM gcr.io/tensorflow/tensorflow:1.5.0-devel-gpu
RUN apt-get update && apt-get install -y \
  git 

RUN apt-get install -y protobuf-compiler \
  python-lxml \
  python-pil  

# change to tensorflow dir
WORKDIR /tensorflow

# clone the models repo
RUN git clone https://github.com/tensorflow/models.git

WORKDIR models/research

RUN protoc object_detection/protos/*.proto --python_out=.
RUN export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim


CMD ["echo", "Running tensorflow docker"]