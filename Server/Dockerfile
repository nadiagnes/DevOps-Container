FROM ubuntu:focal

RUN apt update
RUN apt install ansible ssh sshpass -y
RUN apt install iputils-ping nano -y
RUN service ssh start
RUN echo 'root:password123' | chpasswd
COPY ./sshd_config /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D", "-o", "ListenAddress=0.0.0.0"]
# ENTRYPOINT ["tail"]
# CMD ["-f","/dev/null"]