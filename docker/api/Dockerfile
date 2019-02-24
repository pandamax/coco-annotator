FROM python:3.6

RUN apt-get update && \
        apt-get install -y \
        gunicorn

WORKDIR /workspace

RUN pip install https://download.pytorch.org/whl/cpu/torch-1.0.1.post2-cp36-cp36m-linux_x86_64.whl && \
        pip install torchvision
# Setup flask
COPY requirements.txt requirements.txt
COPY run.py run.py
RUN pip install -r requirements.txt
RUN pip install pycocotools

EXPOSE 5000
CMD python run.py