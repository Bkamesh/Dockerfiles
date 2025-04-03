FROM apache/spark:latest  

USER root

RUN apt-get update && apt-get install -y \
    software-properties-common
    
RUN add-apt-repository ppa:deadsnakes/ppa -y && apt-get update

RUN apt-get install -y \
    python3.12 python3.12-venv python3.12-dev build-essential \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
    
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12 1
    

#RUN ln -sf /usr/bin/python3.12 /usr/bin/python3 

USER spark

