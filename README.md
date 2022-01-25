# ROKS Angular 

## Despliegue en OpenShift desde IBM Cloud shell: 🚀

### Haga 'login' a IBM Cloud desde la línea de comando

Inicialmente debe acceder al shell de IBM Cloud desde el siguiente link:

```
https://cloud.ibm.com/shell
```
<br />

### Acceda al cluster de Open Shift (ROKS) desplegado en IBM Cloud 📦

1.	Inicie sesión e ingrese desde la CLI de OpenShift al clúster en el que se va a trabajar. Para ingresar al clúster que tengamos aprovisionado en nuestra cuenta de IBM Cloud se deben realizar los siguientes pasos:

    * Ingresar a la plataforma de IBM cloud con sus credenciales de inicio de sesión, lo puede hacer desde el siguiente link:

     ```
     https://cloud.ibm.com/
     ```
     <br />
     
    * Diríjase al resource list. Primero debe dar clic en el navigation menu y luego donde dice Resource list, como se puede ver en la siguiente imagen:

      <p align="center">
      <img width="696" alt="7" src="https://user-images.githubusercontent.com/60987042/76996077-da434b00-691e-11ea-92be-558da48f7d97.PNG">
      </p>
      <br />

    * Diríjase a la sección de clústers y dar clic en el que se desea acceder.
      <br />

    * Se da clic en el botón OpenShift web console.
    
      <br />

### Haga 'login' en el cluster de Open Shift (ROKS) desde la linea de comando 📦

Ahora en la parte superior derecha se da clic sobre el ID del correo con el que ingresamos y luego en la sección que dice Copy Login Command.
<br />

<p align="center">
<img width="144" alt="1" src="https://user-images.githubusercontent.com/60987042/76917049-53479180-6890-11ea-91a1-b2c2c9213729.PNG">
</p>
<br />

Y por último volvemos a la terminal que se estaba utilizando pegamos y damos enter.

<br />

### Cree un nuevo proyecto en Open Shift para desplegar las aplicaciones 📦
1.	Cree un nuevo proyecto en el cluster de la siguiente manera:

   ```
   oc new-project <projectname>
   ```
   
   **Nota:** Para el **projectname** coloque **openshift + las iniciales de su nombre y apellido.**
   <br />
   
2.	Acceda al proyecto que acabo de crear de la siguiente manera:

   ```
   oc project <projectname>
   ```   
   <br />

## Despliegue Aplicación Hello World en Angular 🅰️
1.	Clone el repositorio de la aplicación que se desea desplegar.

   **App de hello Word en angular:** https://github.com/emeloibmco/AngularHelloWorld
   
   <br />

2.	Desde el Shell de IBM cloud digite el comando:

   ```
   git clone <url_repositorio>
   ```
   
   <br />
   
3.	Dirigirse desde a esta carpeta con el comando:

   ```
   cd AngularHelloWorld
   ```
   
   <br />
   
4.	Para desplegar la aplicación en OpenShift es necesario escribir el siguiente comando:

   ```
   npx nodeshift --strictSSL=false --dockerImage=nodeshift/ubi8-s2i-web-app --imageTag=10.x --build.env OUTPUT_DIR=dist/angular-web-app --expose
   ```
   <br />
   
   El resultado de este comando va a ser una respuesta de este tipo, que nos indica que la aplicación se desplego correctamente.
   <br />
   
   <p align="center">
   <img width="865" alt="2" src="https://user-images.githubusercontent.com/60987042/76918560-9441a500-6894-11ea-954f-62c8076b8903.PNG">
   </p>
   
   <br />

5.	Para poder acceder al la URL de la aplicación y realizar la verificación de la misma debemos:

      * Acceder a IBM cloud.

      * Dirigirse al resource list.

      * Dirigirse a la sección de clusters.

      * Ingresar al cluster que lleva por nombre openshift-4.2

      * Ingrese a la sección de openshift web console.

      * Buscar el proyecto que creo con sus iniciales y buscar la aplicación que se desplego.

      <br />

   ![image](https://user-images.githubusercontent.com/44415995/83429276-6bdc3800-a3f9-11ea-8b92-51d6032ce830.png)
   
   <br />

   Y por último solo faltaría dar clic en el link que lo llevara a la aplicación desplegada.

   <br />
   
   ![12](https://user-images.githubusercontent.com/60987042/77018166-89494c00-694a-11ea-9f7e-f05d109631d0.png)

   <br />
   
   De esta forma se daría por terminado el despliegue de la aplicación angular en openshift.

   <br />
   

## Despliegue Aplicación Listas en Angular 🅰️ 
1.	Clone el repositorio de la aplicación que se desea desplegar.

   **App de listas en angular:** https://github.com/emeloibmco/AngularWebList

   Desde el Shell de IBM cloud digitar el comando:

   ```
   Git clone <url_repositorio>
   ```
   
   <br />
   
2.	Dirigirse desde a esta carpeta con el comando:

   ```
   cd AngularWebList
   ```
   
   <br />
   
3.	Para desplegar la aplicación en OpenShift es necesario escribir el siguiente comando:

   ```
   npx nodeshift --strictSSL=false --dockerImage=nodeshift/ubi8-s2i-web-app --imageTag=10.x --build.env OUTPUT_DIR=dist/angular-web-app --expose
   ```
   
   <br />
   
4. Para confirmar que la aplicación ha sido desplegada busque la aplicación en el proyecto creado en la consola Web de OpenShift, y seleccione el link con el enlace a la aplicación.

   <p align="center">
   <img width="515" alt="listas" src="https://user-images.githubusercontent.com/60987042/83415347-91ab1200-a3e4-11ea-9df1-90a6ef1e608a.PNG">
    </p>

   Y por último solo faltaría dar clic en el link que lo llevara a la aplicación desplegada.

   <p align="center">
   <img width="681" alt="lis" src="https://user-images.githubusercontent.com/60987042/83415439-adaeb380-a3e4-11ea-8d5c-bf189f652fc1.PNG">
   </p>
   
   <br />
