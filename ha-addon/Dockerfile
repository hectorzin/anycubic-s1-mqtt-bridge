FROM python:3.12-alpine

RUN apk add --no-cache git jq bash ffmpeg

# Clonar el bridge (puedes poner tu fork si quieres probar cambios tuyos)
RUN git clone --depth=1 https://github.com/metheos/anycubic-s1-mqtt-bridge.git /anycubic

WORKDIR /anycubic
RUN pip install --no-cache-dir -r requirements.txt

# Tu run.sh del addon (solo está en el contexto ha-addon)
COPY run.sh /run.sh
RUN sed -i 's/\r$//' /run.sh && chmod +x /run.sh

CMD ["bash", "/run.sh"]
