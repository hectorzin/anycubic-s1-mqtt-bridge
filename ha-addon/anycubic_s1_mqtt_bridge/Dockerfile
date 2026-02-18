FROM python:3.12-alpine

RUN apk add --no-cache jq bash ffmpeg

WORKDIR /anycubic
COPY . /anycubic

RUN pip install --no-cache-dir -r /anycubic/requirements.txt

RUN sed -i 's/\r$//' /anycubic/ha-addon/anycubic_s1_mqtt_bridge/run.sh \
 && chmod +x /anycubic/ha-addon/anycubic_s1_mqtt_bridge/run.sh

CMD ["bash", "/anycubic/ha-addon/anycubic_s1_mqtt_bridge/run.sh"]
