FROM python:3.9.7-slim
ENV PYTHONUNBUFFERED 1

RUN apt-get update &&  \
    apt-get install --no-install-recommends -y \
    git \
    binutils  && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR /code
COPY . /code

RUN pip install --upgrade pip==20.3.3 setuptools==51.0.0
RUN pip install --no-cache-dir -r requirements.txt
CMD [ "/code/.dockerinit.sh" ]
EXPOSE 8000