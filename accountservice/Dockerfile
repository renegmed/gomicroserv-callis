FROM iron/base 
EXPOSE 6767 

ADD accountservice-linux-amd64 /

ADD healthchecker-linux-amd64 /

# execute healthcheck every 3 seconds and accept a timeout of 3 seconds
HEALTHCHECK --interval=3s --timeout=3s CMD ["./healthchecker-linux-amd64", "-port=6767"] || exit 1

ENTRYPOINT ["./accountservice-linux-amd64"]