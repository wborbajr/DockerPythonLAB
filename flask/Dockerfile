# Use the Pyhton 3.7 container image from alpine
#FROM python:3.7-alpine
FROM python:3.7-stretch

# The maintainer of image
MAINTAINER Waldir Borba Junior <wborbajr@gmail.com>

# ensure local python is preferred over distribution python
ENV PATH /usr/local/bin:$PATH

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

# Make sure that we have latest version
RUN \
  pip3 install --upgrade pip && \
  pip3 install pipenv

# Set the work directory to /app
WORKDIR /app

# Copy current directory contents into the container at /app
ADD . /app

# Install the dependencies
RUN pipenv install --system --deploy --ignore-pipfile
# RUN pip install -r requirements.txt

# Run the command to start uWSGI
CMD ["uwsgi", "app.ini"]
