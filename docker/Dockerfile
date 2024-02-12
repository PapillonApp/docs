FROM python:3.9-slim
WORKDIR /app
RUN apt-get update && apt-get install -y git cron
RUN git clone https://github.com/PapillonApp/docs.git .
RUN pip3 install -r requirements.txt
EXPOSE 8000
COPY update.sh /app/update.sh
RUN chmod +x /app/update.sh
RUN crontab -l | { cat; echo "0 * * * * /app/update.sh"; } | crontab -
CMD ["cron", "-f"]
