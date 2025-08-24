FROM ubuntu
MAINTAINER segno

RUN apt-get update && apt-get install -y socat && apt-get clean

RUN useradd -m rop
RUN chown -R root:root /home/rop

# 使用 socat 替代 xinetd
CMD ["socat", "TCP-LISTEN:1337,reuseaddr,fork", "EXEC:/home/rop/run.sh,su=rop"]
