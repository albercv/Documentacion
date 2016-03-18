+++
date = "2016-03-15T17:58:23+01:00"
description = ""
tags = []
title = "Grails"
topics = ["post"]
+++
![](https://grails.github.io/grails-doc/latest/img/grails.png "Grails Framework")
# 1. Instalación del framework Grails
## 1.1  
 Descargar e instalar sdkman  
 En un nuevo terminal introduce

{{< highlight shell >}}
$ "curl -s get.sdkman.io | bash" 
{{< /highlight >}}  

## 1.2  
Sigue los pasos de instalación  
y una vez finalizado introduce el comando  

{{< highlight shell >}}
$ "source $HOME/.sdkman/bin/sdkman-init.sh"
{{< /highlight >}}

## 1.3  
Instala la última versión estable

{{< highlight shell >}}
$ "sdk install grails"
{{< /highlight >}}

## 1.4  
comprueba que Grails se ha instalado  
correctamente con el comando

{{< highlight shell >}}
$ "grails -version"
{{< /highlight >}} 

# 2. Crear un proyecto nuevo desde consola
1. En el directorio deseado

{{< highlight shell >}}
$ "grails create-app 'nombre de la app'"
{{< /highlight >}} 

# 3. Documentación de Grails
1.[Documentacion oficial](https://grails.org/single-page-documentation.html"Grails.org")  
2.[Tutoriales para principiantes](http://grails.asia/grails-tutorial-for-beginners/ "Tutoriales de Grails")