FROM python:3

RUN mkdir /app
WORKDIR /app

COPY simple/requirements.txt /app/requirements.txt
RUN mkdir ~/.pip
COPY pip.conf /root/.pip

RUN pip install -r requirements.txt

#COPY . /app

ENV PYTHONUNBUFFERED 0
ENV PYTHONPATH /app

# notebook
ENV PASSWD='sha1:c702e13800b3:53fcb986946198192d2fbb66fb11304eb87d2b48'
CMD /bin/bash -c 'jupyter notebook --no-browser --ip=0.0.0.0  --port=8888 --NotebookApp.password="$PASSWD"  --allow-root "$@"'

#CMD [ "python", "-u", "main.py"]
