# 1. 基础镜像
FROM openjdk:8-jdk-alpine

# 2. 作者
MAINTAINER user

# 3. 添加 jar 包并重命名为 app.jar
ADD target/*.jar app.jar

# 4. 暴露端口 (xzs 后端默认端口是 8000)
EXPOSE 8000

# 5. 启动命令 (增加了内存限制)
#    -Xms512m: 初始堆内存 512M
#    -Xmx512m: 最大堆内存 512M (通常设为一样，避免动态扩容带来的性能抖动)
ENTRYPOINT ["java", "-Xms512m", "-Xmx512m", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]
