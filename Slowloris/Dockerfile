FROM python:3

ENV HOST=localhost
ENV PORT=80
ENV SOCKETS=150

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD python ./slowloris.py ${HOST} --port=${PORT} --sockets=${SOCKETS}