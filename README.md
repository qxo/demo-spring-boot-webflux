springboot-webflux example
=========================
* run: ` mvn clean spring-boot:run `
* pack: ` mvn clean package `
* test:  `curl -v http://127.0.0.1:8080/api/user/index`

## run with different server
default run with netty
* for tomcat with -Ptomcat: `mvn clean spring-boot:run -Ptomcat`
* for jetty: `mvn clean spring-boot:run -Pjetty`
* for undertow: `mvn clean spring-boot:run -Pundertow`

## enable HTTP/2
* generate keystore
```
keytool -genkey -alias serverkeys -keyalg RSA -keystore server.keystore -storepass secret  -keypass secret -dname "CN=localhost, OU=MYOU, O=MYORG, L=MYCITY, ST=MYSTATE, C=MY" -validity 3650
```
*  copy server.keystore to classpath

*  add needed properties to application.properties:
```
server.http2.enabled=true
server.ssl.key-store=classpath:server.keystore.jks
server.ssl.key-password=secret
```

## References
- [springboot-webflux-functional-restapis](http://javasampleapproach.com/spring-framework/spring-boot/springboot-webflux-functional-restapis )
-  [ springboot-webflux-annotation-based-programming-model]( https://grokonez.com/spring-framework/spring-webflux/springboot-webflux-annotation-based-programming-model)
- https://github.com/developerworks/demo-spring-boot-webflux-annotaion
-  https://github.com/developerworks/demo-spring-boot-webflux-functional
- https://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-web-servers.html
- [404 html ]( https://github.com/h5bp/html5-boilerplate/blob/master/dist/404.html )
- [ blank ico ]( https://www.favicon.cc/?action=icon&file_id=29327)
