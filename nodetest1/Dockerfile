FROM node:4.3.2

RUN useradd --user-group --create-home --shell /bin/false appCMS &&\
npm install --global npm@3.7.5

ENV HOME=/home/appCMS

COPY package.json npm-shrinkwrap.json $HOME/mycms/
RUN chown -R appCMS:appCMS $HOME/*

USER appCMS
WORKDIR $HOME/mycms
RUN npm install

EXPOSE 3000
CMD ["npm", "start"]
