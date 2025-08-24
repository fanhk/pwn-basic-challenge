FROM ubuntu
MAINTAINER segno

RUN apt-get update && apt-get install -y socat && apt-get clean

RUN useradd -m ret2sc
RUN chown -R root:root /home/ret2sc

# 使用 socat 替代 xinetd
CMD ["socat", "TCP-LISTEN:1337,reuseaddr,fork", "EXEC:/home/ret2sc/run.sh,su=ret2sc"]
