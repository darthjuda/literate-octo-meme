# dashbox app Dockerfile
# construction du container hote de l'app :

# a partir de ubuntu 18.04
FROM  ubuntu:18.04

# mise a jour
# install clang
# install cacao framework (GUI)
RUN apt-get -y update && \
  apt-get -y upgrade && \
  apt-get install -y clang \
  apt-get install -y libcairo-dev libsdl2-dev liblcms2-dev

# def variable env
ENV APP_HOME /app

#creation repertoire travail
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

# ADD Design Design
ADD Design Design

# ajout dependance et integration biblio
ADD Package.swift Package.swift
RUN swift package fetch

# ajout fichiers Sources
ADD Sources Sources

# creation de l'executable
RUN swift build
