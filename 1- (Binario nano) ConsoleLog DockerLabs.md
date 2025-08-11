Lanzandole un nmap vemos lo siguente

![[Pasted image 20250130144023.png]]

Por el puerto 3000 tenemos un backend Node.js este se emplea en javascript para poder acciones del lado del servidor

Vemos esto por el puerto 80

![[Pasted image 20250130204820.png]]

vemos que es un boton que aparentemente no hace nada

Hacemos un poco de fuzzing

![[Pasted image 20250130204856.png]]

Vemos el directorio backend que es bastante interesante

![[Pasted image 20250130204911.png]]

Y aqui vemos lo siguente, esto es lo que levanta el puerto 3000

![[Pasted image 20250130205027.png]]

Aqui vemos que un backend esta expuesto con el token y contraseña

Siempre que veamos una pagina web con un boton o algo clickable deberíamos de inspeccionarlo

![[Pasted image 20250130205503.png]]

Si hacemos click y vemos la consola nos saldria esto

![[Pasted image 20250130205545.png]]

Aqui tenemos un recurso que con curl podemos mandarle el token 

![[Pasted image 20250130205824.png]]

![[Pasted image 20250130210008.png]]

Esto es lo que nos devolveria ya que sigue este codigo

![[Pasted image 20250130210718.png]]

Que cuando se manda el token: tokentraviesito, nos devuelve la contraseña

Ya teniendo la contraseña podemos hacer un ataque de fuerza bruta al protocolo ssh por el puerto 5000

![[Pasted image 20250130211003.png]]

![[Pasted image 20250130211035.png]]

Una vez dentro buscamos binarios con los que podamos escalar privilegios

![[Pasted image 20250205204949.png]]

Y vemos que podemos hacerlo con nano

Estas serian las instrucciones en gtfobins

![[Pasted image 20250205205040.png]]

Seguimos las instrucciones

![[Pasted image 20250205205246.png]]

Una vez aqui

![[Pasted image 20250205205303.png]]

Aqui le damos Ctrl + T

Una vez hecho vemos que podemos escribir codigo abajo y escribimos /bin/sh

![[Pasted image 20250205205413.png]]

Y ya seriamos root



