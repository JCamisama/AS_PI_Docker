FROM couchdb:2.3
ENV COUCHDB_USER=supervisor
ENV COUCHDB_PASSWORD=strongpassword
COPY local.ini  /opt/couchdb/etc/
# ADD initialize_database.sh /
# RUN /initialize_database.sh
# RUN service couchdb restart
# RUN curl --location --request PUT 'http://localhost:5984/pieces' --header 'Authorization: Basic c3VwZXJ2aXNvcjpzdHJvbmdwYXNzd29yZA=='
# RUN curl --location --request POST 'http://localhost:5984/pieces' \
# --header 'Content-Type: application/json' \
# --header 'Authorization: Basic c3VwZXJ2aXNvcjpzdHJvbmdwYXNzd29yZA==' \
# --data-raw '{"_id":"_design/pieces", "views": { "byName": { "map": "function (doc) { emit(doc.name, doc.composer);}" }}}'
