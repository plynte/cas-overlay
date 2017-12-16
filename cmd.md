#### log4j2.xml
cas log dir change . ---> /apps/logs/cas



### 生成tomcat HTTPS keystore

keytool -genkeypair -alias tomcat -keyalg RSA -keysize 2048 -validity 3650 \
    -keypass 4QrcOUm6Wau+VuBX8g+IPg== -storepass 4QrcOUm6Wau+VuBX8g+IPg== \
    -keystore /apps/conf/cas/key/tomcat.keystore \
    -dname "CN=cas.example.org,OU=example,O=example.org,L=GZ,ST=GD,C=CN"



#### 把依赖jar包安装到本地maven仓库 ~/.m2/repository
cd cas-overlay-template/lid/
mvn install:install-file \
    -Dfile=cas-server-support-ldap-5.1.1.jar \
    -DgroupId=org.jasig.cas \
    -DartifactId=cas-server-support-ldap \
    -Dversion=5.1.1 \
    -Dpackaging=jar

mvn install:install-file \
    -Dfile=cas-server-support-json-service-registry-5.1.1.jar \
    -DgroupId=org.jasig.cas \
    -DartifactId=cas-server-support-json-service-registry \
    -Dversion=5.1.1 \
    -Dpackaging=jar

mvn install:install-file \
    -Dfile=cas-server-support-jdbc-drivers-5.1.1.jar \
    -DgroupId=org.jasig.cas \
    -DartifactId=cas-server-support-jdbc-drivers \
    -Dversion=5.1.1 \
    -Dpackaging=jar

mvn install:install-file \
    -Dfile=cas-server-support-jdbc-5.1.1.jar \
    -DgroupId=org.jasig.cas \
    -DartifactId=cas-server-support-jdbc \
    -Dversion=5.1.1 \
    -Dpackaging=jar

