FROM python:latest

EXPOSE 8888

RUN mkdir -p /usr/notebooks/

WORKDIR /usr/notebooks

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

CMD jupyter notebook --ip 0.0.0.0 --port 8888 --no-browser --allow-root
