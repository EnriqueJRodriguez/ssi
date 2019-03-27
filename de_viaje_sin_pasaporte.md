# DE VIAJE SIN PASAPORTE

Query to select the users and output the result to a file, tuples only

	select uo from alumnos_ssi_20182019 where pl='PL-08' and not uo='uo258654' \t \o pl8;

## Ejercicio 1

	ssh-keygen -t rsa

## Ejercicio 2

	cat /home/uo258654/.ssh/

## Ejercicio 3

	ssh-copy-id -i ~/.ssh/id_rsa.pub uo258654@192.168.61.140
**AVISO:** falla la primera vez porque en el ejercicio anterior pone que las contraseñas se tienen que cambiar en el primer logeo.

## Ejercicio 4

	ssh uo258654@192.168.61.140
	cat .ssh/authorized_keys

## Ejercicio 5
Copiamos el archivo de la clave pública al de claves autorizadas

	cat .ssh/id_rsa.pub >> .ssh/authorized_keys

Creamos el archivo de clave para que lo entienda putty

	puttygen ./.ssh/id_rsa -o .ssh/id_rsa.ppk

**AVISO:** en el putty, se importan las claves en SSH -> Auth

## Ejercicio 7

	ssh -N -L 1234:localhost:5432 192.168.61.140

Pulsamos Ctrl+z y luego 

	bg

Así tenemos el proceso en el _background_


