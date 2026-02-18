FROM python:3.12-alpine

RUN apk add --no-cache git jq bash ffmpeg

RUN git clone --depth=1 https://github.com/metheos/anycubic-s1-mqtt-bridge.git /anycubic

WORKDIR /anycubic
RUN pip install --no-cache-dir -r requirements.txt

COPY run.sh /anycubic/run.sh
RUN sed -i 's/\r$//' /anycubic/run.sh && chmod +x /anycubic/run.sh

CMD ["bash", "/anycubic/run.sh"]
