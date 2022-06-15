FROM python:3.8

MAINTAINER Andreas Brüniger

WORKDIR /srv
ADD ./requirements.txt /srv/requirements.txt
RUN pip install -r requirements.txt

# TA-Lib
RUN wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz && \
  wget http://savannah.gnu.org/cgi-bin/viewcvs/*checkout*/config/config/config.guess && \
  wget http://savannah.gnu.org/cgi-bin/viewcvs/*checkout*/config/config/config.sub && \
  tar -xvzf ta-lib-0.4.0-src.tar.gz && \
  mv config.guess ta-lib/config.guess && \
  mv config.sub ta-lib/config.sub && \
  cd ta-lib/ && \
  ./configure --prefix=/usr && \
  make && \
  make install

RUN rm -R ta-lib ta-lib-0.4.0-src.tar.gz
