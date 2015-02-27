aplicar plug-in : ' eclipse '
aplicar plug-in : " eclipse-wtp '
aplicar a partir de : ' vaadin.plugin '

versão =  " 0.1-SNAPSHOT '

repositórios {
  	mavenCentral ()
    maven {
        url " http://files.couchbase.com/maven2/ "
    }
    maven {
    	url " http://maven.vaadin.com/vaadin-addons "	
    }
	maven {
		url " http://support.audaxis.com/maven2/ "
	}
	maven {
		url " http://jrimum.org/maven/content/groups/public/ "
	}
	maven {
		url " https://repository.jboss.org/nexus/content/repositories/thirdparty-releases "
	}
	maven {
		url " https://oss.sonatype.org/content/repositories/sourceforge-releases "
	}
}
	
vaadin {
    versão ' 7.3.10 '
    widgetset ' dc.framework.DCWidgetSet '
   	widgetsetGenerator ' dc.framework..OptimizedConnectorBundleLoaderFactory '
    plug-in {
        logToConsole verdade
    }
}
vaadin . gwt . jvmArgs = [ ' -Xmx1024m ' , ' -Xms256M ' , ' -XX: MaxPermSize = 512m ' ]
vaadin . gwt . estrito = false 
 
tarefas . withType ( Compilar ) {
	opções . encoding =  " UTF-8 '
}

dependências {

		 
		 compilar os arquivos ( ' libs / maskedtextfield-0.1.4.jar ' )
		 compilar os arquivos ( ' libs / jrimum / jrimum-bopepo-0.2.3-SNAPSHOT.jar ' )
 		 compilar os arquivos ( ' libs / jrimum / jrimum-domkee-0.2.3-SNAPSHOT.jar ' )
 	     compilar os arquivos ( ' libs / jrimum / jrimum-texgit-0.2.0-SNAPSHOT.jar ' )
 		 compilar os arquivos ( ' libs / jrimum / jrimum-utilix-0.2.3-SNAPSHOT.jar ' )
 		 compilar os arquivos ( ' libs / jrimum / jrimum-Vallia-0.2.3-SNAPSHOT.jar ' )
 		 compilar os arquivos ( ' libs / jrimum / log4j-1.2.15.jar ' )
		  
		 compilar ( ' org.vaadin.addon: confirmdialog: 2.0.5 ' ) {
     		// Excluindo uma dependência transitiva especial:
     		excluir módulo : ' vaadin '  // pelo nome artefato
   			excluir módulo : ' vaadin-server '  // pelo nome artefato
   			excluir módulo : ' vaadin-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-compilados-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-temas '  // pelo nome artefato
   		}
   		
   		 compilar ( ' org.vaadin.addons: feiticeiros-for-vaadin: 1.1.0 ' ) {
     		// Excluindo uma dependência transitiva especial:
     		excluir módulo : ' vaadin '  // pelo nome artefato
   			excluir módulo : ' vaadin-server '  // pelo nome artefato
   			excluir módulo : ' vaadin-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-compilados-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-temas '  // pelo nome artefato
   		}
   		
   		
   		compilar ( ' org.vaadin.addons.lazyquerycontainer: vaadin-lazyquerycontainer: 7.3.3.6 ' ) {
   			excluir módulo : ' vaadin '  // pelo nome artefato
   			excluir módulo : ' vaadin-server '  // pelo nome artefato
   			excluir módulo : ' vaadin-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-compilados-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-temas '  // pelo nome artefato
   			excluir módulo : ' javax.persistence '
   		}
   			
		compilar ( ' org.vaadin.addons: fonticon: 7.1.1 ' ) {
			excluir módulo : ' vaadin '  // pelo nome artefato
   			excluir módulo : ' vaadin-server '  // pelo nome artefato
   			excluir módulo : ' vaadin-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-compilados-client '  // pelo nome artefato
   			excluir módulo : ' vaadin-temas '  // pelo nome artefato
		}
		 
         compilar ' com.vaadin.addon: vaadin-calendário-CVAL-2.0: 2.0.0.beta3 '
         
         // ElCache
         compilar ' net.sf.ehcache: ehcache: 2.8.0 '
         
         
         compilar ' com.vaadin.addon: vaadin-charts: 1.0.0 '
         
         // Compilar 'org.vaadin.addons: maskedtextfield: 0.1.1'
         
         // Compilar 'org.vaadin.addons: canvas: 2.0'
         compilar ' org.vaadin.addons: PopUpButton: 2.5.0 '
        
		// dependências		
		compilar ' org.hibernate: hibernate-core: 4.3.8.Final '
		compilar ' org.hibernate: hibernate-c3p0: 4.3.8.Final '
		compilar ' org.hibernate: hibernate-entitymanager: 4.3.8.Final '
		compilar ' org.hibernate: hibernate-validador: 5.1.3.Final '
		
		compilar ' org.hibernate: hibernate-search: 5.0.1.Final '
		compile ' org.hibernate:hibernate-search-analyzers:5.0.0.Alpha1 ' //'org.hibernate:hibernate-search-analyzers:4.5.3.Final'
		
		
		compilar ' com.itextpdf: itextpdf: 5.5.5 '
		compilar ' javax.mail: mail: 1.4.7 '
		
		compilar ' mysql: mysql-connector-java: 5.1.21 '
		compilar ' org.postgresql: PostgreSQL: 9,4-1200-jdbc41 '
         
		
		compilar ' br.com.caelum.stella: caelum-stella-core: 2.0 beta 1 '
		compilar ' commons-beanutils: commons-beanutils: 1.7.0 '
		compilar ' commons-pool: commons-pool: 1.6 '
		compilar ' commons-lang: commons-lang: 2.6 '
		compilar ' commons-DBCP: commons-DBCP: 1.4 '
						
		compilar ' asm: asm: 3.3.1 '
		compilar ' org.springframework: primavera em grão: 4.1.5.RELEASE '
		compilar ( ' org.springframework: primavera-contexto: 4.1.5.RELEASE ' ) {
			excluir módulo : ' commons-logging "
		}
		
		compilar ' org.springframework: primavera-core: 4.1.5.RELEASE '
		compilar ' org.springframework: primavera-expressão: 4.1.5.RELEASE '
		compilar ' org.springframework: primavera-ORM: 4.1.5.RELEASE '
		compilar ' org.springframework.data:-jpa primavera-data: 1.7.2.RELEASE '
		compilar ' org.springframework: primavera-jdbc: 4.1.5.RELEASE '
		compilar ' org.springframework: primavera-tx: 4.1.5.RELEASE '
		compilar ' org.springframework: primavera-web: 4.1.5.RELEASE '
		compilar ' org.springframework: primavera-webmvc: 4.1.5.RELEASE '
		compilar ' org.springframework: primavera-context-suporte: 4.1.5.RELEASE '
		
		compilar ' org.freemarker: freemarker: 2.3.21 '
		
		
		compilar ' org.springframework.security: spring-security-core: 3.2.5.RELEASE '
		compilar " org.springframework.security: spring-security-web: 3.2.5.RELEASE "
		compilar ' org.springframework.security: spring-security-config: 3.2.5.RELEASE '
		
		
		// CAPTCHA
		compilar ' com.octo.captcha: jcaptcha-api: 1.0 '
	   	compilar ' com.octo.captcha: jcaptcha: 2,0-alfa-1 '	
		compilar ( ' com.octo.captcha: jcaptcha-integração-simple-servlet: 2,0-alfa-1 ' ) {
			excluir módulo : ' servlet-api '
		}
	   
		compilar ' org.slf4j: JCL-over-slf4j: 1.7.10 '
		compilar ' org.slf4j: slf4j-api: 1.7.10 '
		compilar ' ch.qos.logback: logback-clássico: 1.1.2 '
		compilar ' ch.qos.logback: logback-core: 1.1.2 '
		
        // ProvidedCompile 'org.mortbay.jetty: molhe: 6.1.26'
        providedCompile ' org.eclipse.jetty.aggregate: molhe-agregado-projeto: 8.1.16.v20140903 '
        
        // DESCANSO
        compilar ' com.sun.jersey: jersey-servlet: 1.17.1 '
        compilar ' com.sun.jersey: jersey-servidor: 1.17.1 '
        compilar ' com.sun.jersey: jersey-core: 1.17.1 '
        compilar ' com.sun.jersey: jersey-json: 1.17.1 '
        
        compilar ( ' com.sun.jersey.contribs: jersey-mola: 1.17.1 ' ) {
        	excluir grupo : ' org.springframework '
        } 
		
   		
		compilar ' org.vaadin.addon: easyuploads: 7.2.0 '
		compilar ' com.reveregroup.gwt: gwt-image-loader: 1.1.4 '
		compilar ' org.vaadin.addons: imageviewer: 0.5.1.v7 '  
		compilar ' org.vaadin.addons: imagescaler: 2.0.0 '
		compilar ' org.vaadin.addons: imagecarousel: 1.0.3 '
		
		// Relatórios com JasperReports
		compilar ( ' net.sf.jasperreports: jasperreports: 5.5.1 ' ) {
        	excluir grupo : ' eclipse '
        } 
		compilar ' com.lowagie: itext: 2.1.7 '
		compilar ' com.itextpdf: itextpdf: 5.1.2 '
		compilar ' org.codehaus.groovy: Groovy-tudo: 2.1.1 '		
		
		compilar ' org.apache.poi: poi: 3.10-FINAL '
		compilar ' org.apache.poi: poi-OOXML: 3.10-FINAL '
		compilar ' org.apache.poi: poi-rascunho: 3.10-FINAL '
		compilar ' org.apache.poi: poi-OOXML-schemas: 3.10-FINAL '
		compilar ' org.apache.poi: OOXML-schemas: 1.1 '
		compilar ' em tempo Joda: joda-time: 2.3 '
		compilar ' org.apache.commons: commons-lang3: 3.3 '
		
		compilar ' org.vaadin.addons: filteringtable: 0.9.11.v7 '
		compilar ' com.vaadin: vaadin-push: 7.3.10 '
		compilar ( ' it.zero11.vaadin: asyncfiltercombobox: 0.2.0 ' ) {
			excluir grupo : ' com.vaadin '
		}		

		compilar ' org.vaadin.addons: numberfield7: 0.0.1 '
}
