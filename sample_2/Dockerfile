FROM ubuntu:20.04
LABEL Author="John Doe" Description="This is a sample image for Flask app"
RUN ["apt" , "update" , "-y"]
RUN ["apt" , "install" , "-y" , "python3-pip", "python3-dev", "python3", "git"]
EXPOSE 5000
WORKDIR /app
RUN ["git" , "clone" , "https://github.com/Sysnove/flask-hello-world.git"]
WORKDIR /app/flask-hello-world
RUN echo "Flask==2.2.2" > requirements.txt
RUN ["pip" , "install" , "-r" , "requirements.txt"]
# ENTRYPOINT ["python3"]
# CMD ["hello.py"]

