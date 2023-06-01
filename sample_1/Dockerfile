FROM ubuntu:latest
LABEL Author="John Doe" Description="This is a sample image for Flask app"
RUN ["apt" , "update" , "-y"]
RUN ["apt" , "install" , "-y" , "python3-pip", "python3-dev", "python3"]
EXPOSE 5000
COPY ./flask /app
WORKDIR /app
RUN ["pip" , "install" , "-r" , "requirements.txt"]
ENTRYPOINT ["python3"]
CMD ["app.py"]