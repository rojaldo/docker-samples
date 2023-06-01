FROM ubuntu:20.04 AS node_builder
LABEL Author="John Doe" Description="This is a sample image for Flask app"
RUN ["apt" , "update" , "-y"]
#Install nodejs 18 version
RUN ["apt" , "install" , "-y" , "curl"]
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
#Install curl, nodejs and git
RUN ["apt" , "install" , "-y" , "nodejs", "git"]
#clone the repo
RUN ["git" , "clone" , "https://github.com/rojaldo/ng15"]
#workdir
WORKDIR /ng15
#install dependencies
RUN ["npm" , "install"]
#build the app
RUN ["npm" , "run" , "build"]

FROM nginx:latest
#copy the build from nodejs image
COPY --from=node_builder /ng15/dist/ng15 /usr/share/nginx/html
#expose port 8080
EXPOSE 8080
#run the app
WORKDIR /usr/share/nginx/html
ENTRYPOINT ["nginx" , "-g" , "daemon off;"]
