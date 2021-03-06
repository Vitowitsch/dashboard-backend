### A Java-Webapp-Template

##### Tech-Stack
- Java
- Spring-Boot
- MariaDB by JDBC
- H2
- Presto
- Athena
- Docker
- AWS-S3 (can be replaced / monkey-patched for local file-system-access)

##### Configuration
- src/main/resources/application.properties

###### Environment Variables
- EXPECTANCY_S3_BUCKET:
- EXPECTANCY_S3_KEY:
- ATHENA_S3_LOCATION:
- CACHE_ALGO_INPUT_FEATURES: true
- CACHE_ALGO_OUTPUT_FEATURES: true
- INPUT_FEATURES:
- MILEAGE_THRESHOLD: 300
- spring.datasource.driver-class-name: org.mariadb.jdbc.Driver
- spring.datasource.password:
- spring.datasource.url: jdbc:mariadb://127.0.0.1:147/xy
- spring.datasource.username: root
- spring.jpa.database-platform: spring.jpa.database-platform: org.hibernate.dialect.MySQL5Dialect

##### Docker
~~~
docker build -t java-template .
docker run --rm -it -p 9090:9090 java-template
~~~

##### Test
- Java-Persistance-Layer Test use a H2 in-memory database.
- AWS S3-Access Test uses a filesystem and an in-memory-file-system mockup

~~~
mvn clean test
~~~

