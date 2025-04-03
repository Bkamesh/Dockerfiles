FROM apache/airflow:2.10.5 AS final

USER airflow
RUN pip install --no-cache-dir \
    pandas \
    numpy \
    prophet \
    pyodbc \
    apache-airflow-providers-microsoft-mssql \
    apache-airflow-providers-apache-kafka \
    apache-airflow-providers-apache-spark\
    kafka-python

USER root
# Install system dependencies including procps and Java (OpenJDK 17)
RUN apt-get update && apt-get install -y \
    curl \
    gnupg2 \
    procps \
    openjdk-17-jdk \
    unixodbc \
    unixodbc-dev \
    && apt-get update \
    && ACCEPT_EULA=Y apt-get install -y \
        msodbcsql17 \
        mssql-tools \
    && rm -rf /var/lib/apt/lists/*

