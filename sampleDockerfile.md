`FROM node`
from baseImage 

`WORKDIR /app`

`COPY . .` or `COPY . /app`
first dot => outside of the image where the file path where the the dockerfile exist to be copied in the image

second dot where the files and folders should be saved.

`RUN npm install`

`EXPOSE 80`
specifies port for the container (optional but recommended)

`CMD ["node","server.js"]`
when we start the container that will run 
always should be the last instruction

`VOLUME ["/app/feedback"]`
NOTE: better way to do this is to copy package.json in app first then run npm intall then copy the app, in this way it will not run npm install again if we change you code.

COPY package.json /app
RUN nom install
COPY . /app