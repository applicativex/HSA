# Slowloris

Slowloris DoS attack python implementation from https://github.com/gkbrk/slowloris is used. 
Build slowloris docker image as: docker build -t slowloris .
Run slowloris container as: docker run -e HOST=host -e PORT=port -e SOCKETS=sockets slowloris

To mitigate Slowloris DoS Attack custom configuration(nginx.conf) is used for nginx.

Both nginx and slowloris attack containers can be launched from CLI by: docker-compose up --scale slowloris=4
