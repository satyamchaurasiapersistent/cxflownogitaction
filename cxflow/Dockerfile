#Use CxFlow Base image
FROM checkmarx/cx-flow
#Copy script to import certs into Java cacerts keystore

RUN mkdir -p sourcecode

COPY cxflow/scripts/keytool-import-certs.sh /app/keytool-import-certs.sh
COPY certificate/checkmarx.crt /app/certificate.crt
COPY . /app/sourcecode

RUN chmod +x /app/certificate.crt
RUN chmod +x /app/keytool-import-certs.sh
RUN chmod +x /app/sourcecode


COPY cxflow/entrypoint.sh /app/entrypoint.sh
#Make it executable
RUN chmod +x /app/entrypoint.sh
ENTRYPOINT ["/app/entrypoint.sh"]
