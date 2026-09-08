# 1. 指定基础镜像：一个包含了 Java 运行环境的轻量级 Linux 系统
#    这里以 OpenJDK 17 为例，你也可以根据项目需要换成 8, 11, 21 等版本
#    使用 -slim 版本可以大幅减小最终镜像的体积[reference:5]
FROM eclipse-temurin:8-jdk

# 2. 设置容器内的工作目录
WORKDIR /app

# 3. 将你本地的 JAR 包复制到镜像的工作目录中，并重命名为 app.jar
#    注意：请将 'target/your-app-name.jar' 替换成你 JAR 文件的实际路径和名称
COPY target/spring-boot-1-QuickStart-20260413063130.jar app.jar

# 4. 声明容器内应用会监听的端口（通常是 Spring Boot 的 8080 端口）
EXPOSE 8080

# 5. 定义容器启动时执行的命令：运行 JAR 包
#    使用 JSON 数组格式比字符串形式更可靠[reference:6]
ENTRYPOINT ["java", "-jar", "app.jar"]