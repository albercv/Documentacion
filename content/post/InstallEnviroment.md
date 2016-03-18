+++
date = "2016-03-08T13:15:13+01:00"
description = "Instalación de Java, Git, Grails, Ruby y Cucumber"
tags = ["java", "grails", "sdkman", "hugo", "highlight", "IntelliJ", "ssh", "git", "post", "cucumber", "ruby"]
title = "Instalación del entorno"
topics = ["installación", "post"]
+++

### 1. Instalación de Java  

>{{< highlight shell >}}
 sudo add-apt-repository ppa:webupd8team/java
 sudo apt-get update
 sudo apt-get install oracle-java8-installer
{{< /highlight >}}  

     
### 2. Instalación de Grails con SDKMAN  

>{{< highlight shell >}}
 sudo curl -s get.sdkman.io | bash
 source "$home/.sdkman/bin/sdkman-init.sh"
 sudo sdk install grails
{{< /highlight >}}


### 3. Instalación de Git  
>{{< highlight shell >}}
 sudo apt-get install git
{{< /highlight >}}  


### 4. Instalación de IDE IntelliJ  
>a. Descargar de la web  

>>https://www.jetbrains.com/idea/#chooseYourEdition  

>b. Abrir la consola e ir a la ruta en la que se haya descargado IntelliJ  

>>{{< highlight shell >}}
  tar -xvfz ideaIU-15.0.4.tar.gz /usr/lib/
{{< /highlight >}}  


### 5. Crear claves ssh para git  

>a. Comprobar si ya existen claves ssh generadas  

>>{{< highlight shell >}}
 ls -al ~/.ssh
{{< /highlight >}}  

>b. Generar claves ssh en caso de no disponer de ellas  

>>{{< highlight shell >}}
 ssh-keygen -t rsa -b 4096 -C "github_email_account"
{{< /highlight >}}  

>c. Presionar Enter cuando aparezca el mensaje para guardar la clave (la guardará en la localización por defecto)    

>d. Volver a presionar Enter cuando aparezca el mensaje para crear una passphrase, esto hará que no se genere ninguna  

	
### 6. Instalación de Hugo  

>a. Instalación base de Hugo

{{< highlight shell >}}
 cd ~
 wget https://github.com/spf13/hugo/releases/download/v0.14/hugo_0.14_amd64.deb
 sudo dpkg -i hugo*.deb
{{< /highlight >}}  

>b. Comprobar la instalación    
  
>>{{< highlight shell >}}
 hugo version
{{< /highlight >}}  
	
>c. Descargar los Temas  

>>{{< highlight shell >}}
 git clone --recursive https://github.com/spf13/hugoThemes ~/themes
{{< /highlight >}}  
	
>d. Instalar Pygments Syntax Highlighter  

>>{{< highlight shell >}}	
 sudo apt-get install python-pip
 sudo pip install Pygments
{{< /highlight >}}  


### 7. Crear el primer site de Hugo 

>a. Crear árbol de carpetas del proyecto Hugo	

>>{{< highlight shell >}}
 hugo new site ~/my-website
 cd ~/my-website	
 ln -s ../themes
{{< /highlight >}}

>b. Crear el archivo de configuración en la ráiz de la carpeta del proyecto  

>>{{< highlight shell >}}
 nano config.toml
{{< /highlight >}}

>>Dependiendo del tema escogido habrá que crear un archivo de configuración específico

>>Un ejemplo archivo de configuración básico es:

>>>{{< highlight shell >}}
 baseurl = "http://your_domain_or_IP/"
 languageCode = "en-us"
 title = "Your Site Name"
 newContentEditor = "nano"
 theme = "nofancy"
 pygmentsStyle = "native"
{{< /highlight >}}



>c. Crear el primer post: Situarse dentro de la raíz del proyecto hugo

>>{{< highlight shell >}}hugo new post/nombreDelPost.md{{< /highlight >}}

>>Podemos incluir metadatos dentro de cada uno de los post, hugo soporta diferentes formatos para ello:

>>TOML

>>>{{< highlight shell >}}
 +++
 categories = ["misc"]
 date = "2015-11-05T16:58:58-05:00"
 title = "About Me"
 +++

 Hello and welcome to my site!
			
 ## A Bit About Me
	
 I like alpacas and I'm a fan of static sites.
		
 ![Great alpaca picture](https://upload.wikimedia.org/wikipedia/commons/c/c4/Alpaka_33444.jpg)
 {{< /highlight >}}

>>YAML

>>>{{< highlight shell >}}
 ---
 categories: ["misc"]
 date: "2015-11-05T16:58:58-05:00"
 title: "About Me"
 ---

 Hello and welcome to my site!

 ## A Bit About Me

 I like alpacas and I'm a fan of static sites.

 ![Great alpaca picture](https://upload.wikimedia.org/wikipedia/commons/c/c4/Alpaka_33444.jpg)
{{< /highlight >}}

>>JSON
	
>>>{{< highlight shell >}}
		
 {
  "categories": ["misc"],
  "date": "2015-11-05T16:58:58-05:00",
  "title": "About Me"
 } 

  Hello and welcome to my site!
			
  ## A Bit About Me

  I like alpacas and I'm a fan of static sites.
	
  ![Great alpaca picture](https://upload.wikimedia.org/wikipedia/commons/c/c4/Alpaka_33444.jpg)
{{< /highlight >}}  


### 8. Cucumber con Ruby

>a. Instalación de Ruby

>> __I. Compilando el código fuente__

>>>a. Instalar la librería libssl-dev

>>>>{{< highlight shell >}}
sudo apt-get install libssl-dev
{{< /highlight >}}  

>>>b. Descargar el archivo que contiene el código fuente:

>>>> https://www.ruby-lang.org/es/downloads/

>>>c. Descomprimir el archivo

>>>>{{< highlight shell >}}
  tar xvfz nombre_archivo
{{< /highlight >}}  

>>>d. Ejecutar los siguientes comandos para la instalación

>>>>{{< highlight shell >}}
  ./configure
  make
  sudo make install
{{< /highlight >}}  

>> __II. Desde el repositorio__

>>>{{< highlight shell >}}
  sudo apt-add-repository ppa:brightbox/ruby-ng
  sudo apt-get update
  sudo apt-get install ruby2.3
{{< /highlight >}}

>b. Instalación de Cucumber

>>{{< highlight shell >}}
  sudo gem install cucumber
{{< /highlight >}}