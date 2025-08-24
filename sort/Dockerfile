FROM ubuntu
MAINTAINER segno

RUN apt-get update && apt-get install -y socat && apt-get clean

RUN useradd -m sort
RUN chown -R root:root /home/sort

# 使用 socat 替代 xinetd
CMD ["socat", "TCP-LISTEN:1337,reuseaddr,fork", "EXEC:/home/sort/run.sh,su=sort"]
