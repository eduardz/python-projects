FROM alpine:3.16.2

# Install files
RUN apk add --update --no-cache py3-pip python3 && ln -sf python3 /usr/bin/python

# Copy files
COPY . /app
WORKDIR /app
COPY requirements.txt /app/requirements.txt

# App user
RUN adduser --disabled-password alpine
RUN chown -R alpine:alpine /app
RUN chmod 755 /app 
User alpine

ENV PATH="${PATH}:/home/alpine/.local/bin"

RUN pip3 install --user alpine --no-cache --upgrade pip setuptools
RUN pip3 install --user alpine --no-cache-dir -r requirements.txt

ENTRYPOINT ["python3"]
CMD ["app.py"]
