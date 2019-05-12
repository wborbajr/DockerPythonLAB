# Use the Pyhton 3.7 container image from alpine
#FROM python:3.7-alpine
#FROM alpine:latest
FROM python:3.7-stretch

# The maintainer of image
MAINTAINER Waldir Borba Junior <wborbajr@gmail.com>

# ensure local python is preferred over distribution python
ENV PATH /usr/local/bin:$PATH

ENV PYTHONUNBUFFERED 1

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

# Uncomment lines below if you are working with alpine:latest image
#ENV PACKAGES="\
#  zsh \
#  git \
#  tzdata \
#  python3-dev \
#  py3-setuptools \
#"

# Uncomment lines below if you are working with alpine:latest image
# Installing packages
#RUN \
#  apk --no-cache add --update $PACKAGES

# Make sure that we have latest version
RUN \
  pip3 install --upgrade pip && \
  pip3 install pipenv

# Create the working directory (and set it as the working directory)
RUN mkdir -p /app/web
WORKDIR /app/web

# Install the package dependencies (this step is separated
# from copying all the source code to avoid having to
# re-install all python packages defined in requirements.txt
# whenever any source code change is made)
ADD Pipfile* /app/web/
ADD requirements.txt /app/web/

# Install the dependencies
RUN pipenv install --system --deploy --ignore-pipfile
#RUN pip install --no-cache-dir -r requirements.txt

# Copy the source code into the container
ADD . /app/web

#EXPOSE 8080
#CMD ["gunicorn"  , "-b", "0.0.0.0:8080", "wsgi:app"]
