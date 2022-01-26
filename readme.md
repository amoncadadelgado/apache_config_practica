# Configuración del servidor apache

### En el archivo **httpd.conf**:
~~~
Ubicamos las siguientes lineas:

DocumentRoot "/usr/local/apache2/htdocs"
<Directory "/usr/local/apache2/htdocs">

Se colocan las rutas completas de la carpeta que contiene las paginas web. 
~~~

~~~
Ubicamos las siguientes lineas y las desconmentamos:

# Virtual hosts
Include conf/extra/httpd-vhosts.conf

Activación que permite trabajar con virtualhost.
~~~

### En el archivo **httpd-vhosts.conf**, ubicado dentro de la carpeta extra:
~~~
Introducimos 2 virtualhost:

<VirtualHost primera.example.com:80>
    ServerAdmin webmaster@dummy-host.example.com
    DocumentRoot "/usr/local/apache2/htdocs/primera"
    ServerName example.com
    ServerAlias primera.example.com
    ErrorLog "logs/dummy-host.example.com-error_log"
    CustomLog "logs/dummy-host.example.com-access_log" common
</VirtualHost>

<VirtualHost segunda.example.com:80>
    ServerAdmin webmaster@dummy-host2.example.com
    DocumentRoot "/usr/local/apache2/htdocs/segunda"
    ServerName example.com
    ServerAlias segunda.example.com
    ErrorLog "logs/dummy-host2.example.com-error_log"
    CustomLog "logs/dummy-host2.example.com-access_log" common
</VirtualHost>
~~~
Donde:
- DocumentRoot: Especifica la ruta que contendra los dos documentos necesarios del subdominio.
- ServerName: Especifica el nombre del dominio.
- ServerAlias: Especifica el nombre del subdominio.