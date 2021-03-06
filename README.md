plugins {
    id "fi.jasoft.plugin.vaadin" version "0.9.8"
}


apply plugin: 'eclipse'
apply plugin: 'idea'
apply plugin: 'eclipse-wtp'
apply plugin: 'jetty'

version = '0.1-SNAPSHOT'


repositories {
    mavenCentral()
    maven {
        url "http://files.couchbase.com/maven2/"
    }
    
    
    maven{
        url "http://maven.vaadin.com/vaadin-addons"
    }
    
    maven{
        url "http://support.audaxis.com/maven2/"
    }
    
    maven{
        url "http://jrimum.org/maven/content/groups/public/"
    }
    maven{
        url "https://repository.jboss.org/nexus/content/repositories/thirdparty-releases"
    }
    
    maven{
        url "https://oss.sonatype.org/content/repositories/sourceforge-releases"
    }
    
}



vaadin {
    //7.5.0
    //7.3.10
    version '7.5.0'
    widgetset 'dc.framework.DCWidgetSet'
    widgetsetGenerator 'dc.framework.OptimizedConnectorBundleLoaderFactory'
    plugin {
        logToConsole false
    }
    
}

vaadin.gwt.strict=true
vaadin.plugin.logToConsole=true
vaadin.gwt.gwtSdkFirstInClasspath = true

tasks.withType(JavaCompile) {
    options.encoding = 'UTF-8'
}

task explodedWar(type: Copy) {

    into "$buildDir/exploded"

    with war

}

jettyRun {
    contextPath = ''
}


configurations.compile.exclude module: 'asm'

configurations {
    'vaadin-client' {
    }
}

dependencies {
    compile files('libs/maskedtextfield-0.1.4.jar')
    compile files('libs/jrimum/jrimum-bopepo-0.2.3-SNAPSHOT.jar')
    compile files('libs/jrimum/jrimum-domkee-0.2.3-SNAPSHOT.jar')
    compile files('libs/jrimum/jrimum-texgit-0.2.0-SNAPSHOT.jar')
    compile files('libs/jrimum/jrimum-utilix-0.2.3-SNAPSHOT.jar')
    compile files('libs/jrimum/jrimum-vallia-0.2.3-SNAPSHOT.jar')
    compile files('libs/jrimum/log4j-1.2.15.jar')

    //compile ('org.slf4j:log4j-over-slf4j:1.7.10')
    compile ('org.slf4j:log4j-over-slf4j:1.7.12')
    compile('com.vaadin:vaadin-server:7.5.1')
    compile('com.vaadin:vaadin-client:7.5.1')

    compile('org.vaadin.addon:confirmdialog:2.1.3') {
        //compile('org.vaadin.addon:confirmdialog:2.1.2'){
        //excluding a particular transitive dependency:
        exclude module: 'vaadin' //by artifact name
        exclude module: 'vaadin-server' //by artifact name
        exclude module: 'vaadin-client' //by artifact name
        exclude module: 'vaadin-client-compiled' //by artifact name
        exclude module: 'vaadin-themes' //by artifact name
    }

    compile('org.vaadin.addons:wizards-for-vaadin:1.1.0'){
        //excluding a particular transitive dependency:
        exclude module: 'vaadin' //by artifact name
        exclude module: 'vaadin-server' //by artifact name
        exclude module: 'vaadin-client' //by artifact name
        exclude module: 'vaadin-client-compiled' //by artifact name
        exclude module: 'vaadin-themes' //by artifact name
    }


    compile('org.vaadin.addons.lazyquerycontainer:vaadin-lazyquerycontainer:7.4.0.1'){
        exclude module: 'vaadin' //by artifact name
        exclude module: 'vaadin-server' //by artifact name
        exclude module: 'vaadin-client' //by artifact name
        exclude module: 'vaadin-client-compiled' //by artifact name
        exclude module: 'vaadin-themes' //by artifact name
        exclude module: 'javax.persistence'
    }


    //compile 'com.vaadin.addon:vaadin-charts:2.0.0'
    //compile 'org.vaadin.addons:maskedtextfield:0.1.1'
    //compile 'org.vaadin.addons:canvas:2.0'
    //compile 'org.vaadin.addons:numberfield7:0.0.1'
    //compile 'com.vaadin.addon:vaadin-calendar-cval-2.0:2.0.0'
    //compile 'org.vaadin.addons:imagecarousel:1.0.3'


    compile 'com.reveregroup.gwt:gwt-image-loader:1.1.4'

    compile 'org.vaadin.addons:imagescaler:2.0.0'

    //compile 'org.vaadin.addons:popupbutton:2.5.0'
    compile 'org.vaadin.addons:popupbutton:2.6.0'


    //compile 'org.vaadin.addons:filteringtable:0.9.11.v7'
    compile 'org.vaadin.addons:filteringtable:0.9.12.v7'
    //compile 'com.vaadin:vaadin-push:7.3.10'
    compile 'com.vaadin:vaadin-push:7.5.1'
    compile ('it.zero11.vaadin:asyncfiltercombobox:0.2.0'){
        exclude group:'com.vaadin'
    }


    compile 'com.google.code.gson:gson:2.2'
    compile 'org.vaadin.addons:imageviewer:0.5.1.v7'
    compile 'org.vaadin.addon:easyuploads:7.4.1'

    // ElCache
    compile 'net.sf.ehcache:ehcache:2.10.0'


    // dependencies
    compile 'org.hibernate:hibernate-core:4.3.10.Final'
    compile 'org.hibernate:hibernate-c3p0:4.3.10.Final'
    compile 'com.mchange:c3p0:0.9.5'
    compile 'org.hibernate:hibernate-entitymanager:4.3.10.Final'
    compile 'org.hibernate:hibernate-validator:4.3.2.Final'

    compile 'org.hibernate:hibernate-search:5.3.0.Final'
    compile 'org.hibernate:hibernate-search-analyzers:5.0.0.Alpha1'//'org.hibernate:hibernate-search-analyzers:4.5.3.Final'


    compile 'com.itextpdf:itextpdf:5.5.5'
    compile 'javax.mail:mail:1.4.7'

    compile 'mysql:mysql-connector-java:5.1.21'
    compile ('org.postgresql:postgresql:9.4-1201-jdbc41') {
        exclude module: 'slf4j-simple'
    }

    compile 'br.com.caelum.stella:caelum-stella-core:2.0-beta1'
    compile 'commons-beanutils:commons-beanutils:1.7.0'
    compile 'commons-pool:commons-pool:1.6'
    compile 'commons-lang:commons-lang:2.6'
    compile 'commons-dbcp:commons-dbcp:1.4'

    compile 'org.springframework:spring-beans:4.1.6.RELEASE'
    compile ('org.springframework:spring-context:4.1.6.RELEASE') {
        exclude module: 'commons-logging'
    }

    compile 'org.springframework:spring-core:4.1.6.RELEASE'
    compile 'org.springframework:spring-expression:4.1.6.RELEASE'
    compile 'org.springframework:spring-orm:4.1.6.RELEASE'
    compile 'org.springframework.data:spring-data-jpa:1.7.2.RELEASE'
    compile 'org.springframework:spring-jdbc:4.1.6.RELEASE'
    compile 'org.springframework:spring-tx:4.1.6.RELEASE'
    compile 'org.springframework:spring-web:4.1.6.RELEASE'
    compile 'org.springframework:spring-webmvc:4.1.6.RELEASE'
    compile 'org.springframework:spring-context-support:4.1.6.RELEASE'

    //compile 'org.freemarker:freemarker:2.3.21'
    compile 'org.freemarker:freemarker:2.3.22'

    compile 'org.springframework.security:spring-security-core:4.0.1.RELEASE'
    compile "org.springframework.security:spring-security-web:4.0.1.RELEASE"
    compile 'org.springframework.security:spring-security-config:4.0.1.RELEASE'


    // CAPTCHA
    compile 'com.octo.captcha:jcaptcha-api:1.0'
    compile 'com.octo.captcha:jcaptcha:2.0-alpha-1'
    compile ('com.octo.captcha:jcaptcha-integration-simple-servlet:2.0-alpha-1'){
        exclude module: 'servlet-api'
    }

    compile 'org.slf4j:jcl-over-slf4j:1.7.12'
    compile 'org.slf4j:slf4j-api:1.7.12'
    //compile 'org.slf4j:slf4j-api:1.7.10'
    compile 'ch.qos.logback:logback-classic:1.1.2'
    compile 'ch.qos.logback:logback-core:1.1.2'

    // REST
    compile 'com.sun.jersey:jersey-servlet:1.17.1'
    compile 'com.sun.jersey:jersey-json:1.17.1'
    compile 'com.sun.jersey:jersey-server:1.17.1'
    compile 'com.sun.jersey:jersey-core:1.17.1'

    compile ('com.sun.jersey.contribs:jersey-spring:1.17.1') {
        exclude group:'org.springframework'
    }



    // Reports with JasperReports
    compile ('net.sf.jasperreports:jasperreports:5.5.1') {
        exclude group:'eclipse'
    }
    compile 'com.lowagie:itext:2.1.7'
    compile 'com.itextpdf:itextpdf:5.1.2'
    compile 'org.codehaus.groovy:groovy-all:2.1.1'

    compile 'org.apache.poi:poi:3.10-FINAL'
    compile 'org.apache.poi:poi-ooxml:3.10-FINAL'
    compile 'org.apache.poi:poi-scratchpad:3.10-FINAL'
    compile 'org.apache.poi:poi-ooxml-schemas:3.10-FINAL'
    compile 'org.apache.poi:ooxml-schemas:1.1'
    compile 'joda-time:joda-time:2.3'
    compile 'org.apache.commons:commons-lang3:3.3'

}
