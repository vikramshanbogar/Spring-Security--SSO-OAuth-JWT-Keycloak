FROM gradle:jdk17-focal as build

WORKDIR /saml-app

COPY src ./src/
COPY build.gradle ./

RUN gradle --no-daemon bootJar

FROM eclipse-temurin:17.0.6_10-jdk-focal as prod
ENV TZ=Europe/Berlin
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
WORKDIR /opt/app

COPY --from=build /saml-app/build/libs/*.jar  /opt/app
CMD ["java","-jar", "saml-app.jar"]
