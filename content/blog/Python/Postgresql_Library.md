---
title: 'Python PostgreSQL Library'
date: 2019-12-06 17:30:13
category: 'python'
---

# 1. 설치방법

    # For mac
    brew install openssl@1.1
    export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/opt/openssl/lib/

    brew install libxml2 libxmlsec1 pkg-config
    brew install postgresql

    pip install psycopg2
    # or
    pip3 install psycopg2

# 2. Python code

    import psycopg2

    def connection_test(host, port, user, password):
        try:
            conn = psycopg2.connect(host=host, port=port, user=user, password=password, dbname="dbname")
            cur = conn.cursor()
            cur.close()
            conn.close()
            return "success"

        except Exception as e:
            print("error", e)
            return "failed"
