FROM node:13

RUN mkdir -p /home/webapp
# アプリケーションの依存関係をインストールする
# ワイルドカードを使用して、package.json と package-lock.json の両方が確実にコピーされるようにします。
# 可能であれば (npm@5+)
COPY package*.json  /home/webapp
WORKDIR /home/webapp
RUN npm install pm2 -g
#RUN source ~/.bash_profile
RUN npm install
COPY . /home/webapp
EXPOSE 8080
#CMD [ "node", "app.js" ]
#CMD [ "node", "--prof", "app.js" ]
CMD [ "node", "--require", "pprof", "app.js" ]
#CMD [ "pm2", "start", "--no-daemon", "-i", "max", "app.js" ]
