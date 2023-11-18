# Docker Image 만들기
0. npm i
1. npm run build
2. docker build -t myweb .
3. docker run -d -p 3000:80 --name myweb1 myweb