# 使用 Node.js 官方镜像作为基础镜像
FROM node:18

# 设置工作目录
WORKDIR /app

# 复制 package.json 和 package-lock.json
COPY package*.json ./

# 安装 Hexo 和项目依赖
RUN npm install -g hexo-cli && npm install

# 复制整个项目到容器中
COPY . .

# 生成静态文件
RUN hexo generate

# 暴露端口（Hexo 默认使用 5000 端口）
EXPOSE 5000

# 启动 Hexo 服务器
CMD ["hexo", "server"]
