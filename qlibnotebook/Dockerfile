FROM lballabio/quantlib-python
MAINTAINER Alberto Rios <albertorios94@gmail.com>
LABEL Description="An IPython notebook server with the QuantLib Python module available"

RUN apt-get update \
  && DEBIAN_FRONTEND=noninteractive \
  apt-get install -y ipython-notebook \
    python-pip \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

COPY requirements.txt /requirements.txt

RUN pip install --upgrade pip && pip install -r /requirements.txt

ADD notebooks /notebooks

CMD ipython notebook --no-browser --ip=0.0.0.0 --port=8888 --notebook-dir=/notebooks
