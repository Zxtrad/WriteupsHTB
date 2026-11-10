# NMAP

### Escaneo con Nmap y descubir los puertos abiertos

![](_attachment/enigma-nmap-scan1.png)

### Servicios descubriertos 

![](_attachment/scan-nmap-2.png)

- La presencia de POP3, IMAP (normal y tls), indica que muy probablemente el objetivo tenga una infraestructura de e-mail, ademas de tener un servidor nfs el cual llama mucho la atencion, ya que al este no estar bien configurado puede exponer archivos o directorios a usuarios no autorizados.
  
  - Ejecute: `showmount -e [ip destino]` para mostrar la lista de todos los directorios que el servidor está compartiendo y qué IPs tienen permiso para verlos.

![](_attachment/Pasted%20image%2020261110115402.png)

lo del final nos indica que cualquier ip puede verlos
 
- Montare la carpeta y reviso el contenido 
`$ mkdir /tmp/nfs_results`
`$ sudo mount -t nfs [IP destino]`
`$ ls -la /tmp/nfs_results`
