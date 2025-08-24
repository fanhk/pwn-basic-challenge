FROM ubuntu
MAINTAINER segno

RUN apt-get update && apt-get install -y socat && apt-get clean

RUN useradd -m bof
RUN chown -R root:root /home/bof

# 使用 socat 替代 xinetd
CMD ["socat", "TCP-LISTEN:1337,reuseaddr,fork", "EXEC:/home/bof/run.sh,su=bof"]
