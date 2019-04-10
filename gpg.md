# GnuPG: cifrado y firmado

## Cifrado y descifrado de fichero mediante clave simétrica
Ciframos el archivo con el comando:

	gpg --symmetric --cipher-algo AES256 file.txt

Y se nos pedirá una clave, habiendo escogido en este caso __somier__ .
Ahora, después de recuperar el archivo, lo desciframos usando

       gpg -o ElSecreto.txt -d ElSecrehtoh.txt.gpg
       
E introducimos la contraseña.

## Generar una pareja de claves pública/privada con cert. de revocación
Generamos las claves (y el certificado de revocación) con el comando:

	  gpg --gen-key
	  gpg --output certificadoRev.asc --gen-revoke nombre

Preguntará por un nombre e email. Como contraseña se pondrá __software__ . Para exportarlo, se usa el comando:

	   gpg --export --armor nombre > miClavePublica.asc

Y para importarlo:

  gpg --import miClavePublica.asc


## Cifrar y enviar un documento
Ciframos el documneto __somier.txt__ mediante el comando:

	 gpg --output somier.gpg --encrypt --recipient nombre somier.txt

Para descifrarlo se usa el comando:

     gpg --output somier.txt --decrypt somier.gpg

## Firmar y verificar firmas

Procedemos a firmar uno de los documentos ( __patata.txt__ ):

	   gpg --output patata.sig --sign patata.txt


## Referencias
Encriptación asimértrica: https://www.gnupg.org/gph/en/manual/x110.html
Generar claves pública/privada y cert: https://www.gnupg.org/gph/en/manual/c14.html