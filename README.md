FROM nginx:alpine
COPY index.html /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]



docker build -t static-website .
docker run -d -p 8080:80 --name static-website-container static-website
