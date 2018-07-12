# Instalación de plugin Maven para realizar deploy en weblogic

Primero se debe posicionar en el directorio home de weblogic, para luego navegar a la siguiente ruta
```bash
\oracle_common\plugins\maven\com\oracle\maven\oracle-maven-sync\12.2.1
```
para realizar la instalación de la dependencia en maven local se debe ejecutar el siguiente comando
```bash
mvn install:install-file -DpomFile="oracle-maven-sync-12.2.1.pom" -Dfile="oracle-maven-sync-12.2.1.jar"
```
Para validar la instalación
```bash
mvn help:describe -Dplugin="com.oracle.maven:oracle-maven-sync" -Ddetail​
```

El siguiente paso es utilizar este artefacto e iniciar la sincronización. Esto se hace ejecutando esta línea:
 ````bash
​mvn com.oracle.maven:oracle-maven-sync:push -DoracleHome=$ORACLE_HOME
````

Instalar los arquetipos de Oracle
```bash
mvn archetype:crawl -Dcatalog=C:\Users\Carlos Tapia\.m2/repository/archetype-catalog.xml
```

finalmente se debe agregar las siguiente lineas al archivo  `~/.m2/settings.xml​`

```xml
<pluginGroups>
​    <pluginGroup>com.oracle.weblogic</pluginGroup>
</pluginGroups>
```