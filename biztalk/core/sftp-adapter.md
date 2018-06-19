---
title: Adaptador SFTP | Documentos de Microsoft
description: Crear o configurar una ubicación de recepción y el puerto de envío mediante el adaptador SFTP en BizTalk Server, incluyendo Preguntas frecuentes con el adaptador SFTP
ms.custom: ''
ms.date: 02/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f64c4c8-64a0-4e43-9660-b5c2d75d28aa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d28c3b453ab3e704ddbb06ed42b23dc641a6711
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "29564412"
---
# <a name="sftp-adapter"></a>Adaptador SFTP
BizTalk Server incluye un **SFTP** adaptador para enviar y recibir mensajes desde un servidor FTP seguro mediante el protocolo de transferencia de archivos SSH. Este tema incluyen los pasos para configurar un **SFTP** ubicación de recepción y configurar un puerto de envío SFTP para recibir y enviar mensajes desde un servidor FTP seguro. También incluye preguntas y respuestas más comunes.

## <a name="prerequisites"></a>Requisitos previos
**A partir de 2016 de BizTalk Server**, el adaptador SFTP utiliza WinSCP para conectarse a SFTP y, por tanto, admite una mayor servidores de intervalo de SFTP. **Descargar [WinSCP](http://winscp.net)**  en el tiempo de ejecución de BizTalk Server. Asegúrese de comprobar las versiones admitidas de WinSCP [requisitos de Hardware y Software](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)

BizTalk Server 2013 R2 y versiones anteriores no admiten WinSCP.
  
## <a name="configure-the-receive-location"></a>Configurar la ubicación de recepción
  
> [!NOTE]
>  Antes de crear la ubicación de recepción, debe haber agregado un puerto de recepción unidireccional. Vea [crear un puerto de recepción](../core/how-to-create-a-receive-port.md) para conocer los pasos específicos.  
  
 
1.  En la consola de administración de BizTalk Server, expanda el servidor BizTalk Server, **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear una ubicación de recepción.  
  
2.  En el panel izquierdo, haga clic en el nodo **Puertos de recepción** y, en el panel derecho, haga clic con el botón derecho en el puerto de recepción al que desea asociar la nueva ubicación de recepción y, a continuación, haga clic en **Propiedades**.  
  
3.  En el panel de la izquierda del cuadro de diálogo **Propiedades de puerto de recepción** , seleccione **Ubicaciones de recepción**y, en el panel de la derecha, haga clic en **Nueva** para crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo la **transporte** sección, seleccione **SFTP** desde el **tipo** la lista desplegable y, a continuación, Haga clic en **configurar** para configurar las propiedades de transporte para la ubicación de recepción.  
  
5.  En el **propiedades de transporte SFTP**, realice lo siguiente:  
 
     **Otros**
         
    |Use|Para|  
    |--------------|----------------|  
    |Límite de conexiones|Especificar el número máximo de conexiones simultáneas que se pueden abrir con el servidor.<br /><br /> Esta configuración es por servidor y por ubicación de recepción. Considere los casos siguientes:<br /><br /> -Hay dos ubicaciones de recepción que tienen los mismos valores de propiedad de configuración, incluida la propiedad ConnectionLimit establecida en el mismo valor. Por ejemplo, la propiedad se establece en 6. En este caso, hay una conexión de grupo (con 6 conexiones disponibles) que se utiliza las ubicaciones de recepción.<br /><br /> -Hay dos ubicaciones de recepción configuradas con los mismos valores de configuración y tienen la propiedad ConnectionLimit establecida en valores diferentes. Por ejemplo, la propiedad ReceiveLocation1 está establecida en 6 y la propiedad ReceiveLocation2 se establece en 5. En este caso, cada ubicación de recepción tiene su propio grupo de conexión con sus propias conexiones disponibles. El grupo de conexiones ReceiveLocation1 tiene 6 conexiones disponibles. El grupo de conexiones ReceiveLocation2 tiene 5 conexiones disponibles.|  
    |Log | Disponible a partir de 2016 de BizTalk Server. <br/><br/>Escriba la ruta de acceso completa para crear un archivo de registro de cliente. Utilice este archivo de registro para solucionar los errores.|
  
     **Sondeo**  
  
    |Use|Para|  
    |--------------|----------------|  
    |Intervalo de sondeo|Especifique los intervalos en el que el adaptador sondea el servidor. Para efectuar un sondeo continuo, establezca este valor en cero.<br /><br /> **Valor predeterminado:** 5|  
    |Unidad|Especifica la unidad en la que se ha especificado el intervalo de sondeo, por ejemplo, segundos, minutos, horas o días.<br /><br /> **Valor predeterminado:** segundos|  
  
     **Proxy** (disponible a partir de BizTalk Server 2013 R2)  
  
    |Use|Para|  
    |--------------|----------------|  
    |Dirección|Especifica el nombre DNS o la dirección IP del servidor proxy.|  
    |Contraseña|Especifica la contraseña para el servidor proxy.|  
    |Puerto|Especifica el puerto para el servidor proxy.|  
    |Tipo|Especifica el protocolo que usa el servidor proxy.|  
    |UserName|Especifica el nombre de usuario para el servidor proxy.|  
  
     **Seguridad**  
  
    |Use|Para|  
    |--------------|----------------|  
    |Acepta cualquier clave de Host del servidor SSH|Cuando **True**, la ubicación de recepción acepta cualquier clave de host pública SSH del servidor. Cuando **False**, la ubicación de recepción utiliza la huella digital del servidor para la autenticación. Escriba la huella digital de la **SSHServerHostKeyFingerPrint** propiedad.<br /><br /> **Valor predeterminado:** False|  
    |Modo de autenticación de cliente|Seleccione el método de autenticación que utiliza la ubicación de recepción para autenticar al cliente en el servidor SSH. Si establece en **contraseña**, debe escribir el valor en el **contraseña** propiedad. Si establece en **PublicKeyAuthentication**, debe escribir la clave privada del usuario en el **PrivateKey** propiedad. Si establece en **MultiFactorAuthentication** debe escribir **nombre de usuario** con su **contraseña** y **PrivateKey**. Además, si la clave privada está protegida por una contraseña, escriba la contraseña, así como para la **PrivateKeyPassword** propiedad.<br /><br /> **Valor predeterminado:** contraseña|  
    |Cifrado |Disponible a partir de BizTalk Server 2013 R2. <br/><br/>Especifique el tipo de cifrado.<br/><br/>Opciones de BizTalk Server 2013 R2: Auto, AES y TripleDES<br/><br/>Opciones de BizTalk Server 2016: automática, AES, Arcfour, Blowfish, TripleDES y DES|  
    |Contraseña|Especifique la contraseña de usuario SFTP si ha definido la **ClientAuthenticationMode** a **contraseña**.|  
    |Clave privada|Especifique la clave privada para el usuario SFTP si ha definido la **ClientAuthenticationMode** a **PublicKeyAuthentication**.<br /><br /> **Nota:** el archivo de clave privada debe ser el archivo especificado. ppk.|  
    |Contraseña de clave privada|Especifique una contraseña de clave privada, si es necesario para la clave especificada en el **PrivateKey** propiedad.|  
    |Host del servidor SSH clave huellas digitales|Especifica la huella digital de la clave de host pública para el servidor SSH.|  
    |Nombre de usuario|Especifica la contraseña para iniciar sesión en el servidor SFTP.|  
  
     **SSH Server**  
  
    |Use|Para|  
    |--------------|----------------|  
    |Máscara de archivo|Especifica la máscara de archivo para usar al recibir archivos de un servidor seguro de FTP.|  
    |Ruta de acceso de carpeta|Especifica la ruta de la carpeta en el servidor seguro FTP desde donde la ubicación de recepción puede recuperar archivos.|  
    |Puerto|Especifica la dirección del puerto del servidor FTP seguro en el que tiene lugar la transferencia del archivo.|  
    |Dirección del servidor|Especifica el nombre de servidor o la dirección IP del servidor FTP seguro.|  
  
6.  Haga clic en **Aceptar**.  
  
7.  Especifique los valores apropiados en el cuadro de diálogo **Propiedades de la ubicación de recepción** para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).
 
## <a name="configure-the-send-port"></a>Configurar el puerto de envío  
  
1.  En la consola de administración de BizTalk Server, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **SFTP** para el **tipo** opción en el **transporte** sección de la **General** ficha.  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** botón.  
  
3.  En el **propiedades de transporte SFTP**, escriba lo siguiente:  
  
    **Otros**
    
    |Use|Para|  
    |--------------|----------------|  
    |Límite de conexiones|Especificar el número máximo de conexiones simultáneas que se pueden abrir con el servidor.|  
    |Log | Disponible a partir de 2016 de BizTalk Server. <br/><br/>Escriba la ruta de acceso completa para crear un archivo de registro de cliente. Utilice este archivo de registro para solucionar los errores.|
    |Carpeta temporal | Disponible a partir de BizTalk Server 2013 R2. <br/><br/>Una carpeta temporal en el servidor SFTP para cargar archivos grandes antes de que se puedan mover de forma atómica a la ubicación necesaria en el mismo servidor.|  
    
    **Proxy** (disponible a partir de BizTalk Server 2013 R2)
    
    |Use|Para|  
    |--------------|----------------|  
    |Dirección|Especifica el nombre DNS o la dirección IP del servidor proxy.|  
    |Contraseña|Especifica la contraseña para el servidor proxy.|  
    |Puerto|Especifica el puerto para el servidor proxy.|  
    |Tipo|Especifica el protocolo que usa el servidor proxy.|  
    |Nombre de usuario|Especifica el nombre de usuario para el servidor proxy.|  
    
    **Seguridad**
    
    |Use|Para|  
    |--------------|----------------|  
    |Obtener acceso a cualquier clave de Host del servidor SSH|Cuando **True**, el puerto de envío acepta cualquier clave de host pública SSH del servidor. Cuando **False**, el puerto coincide con la clave de host con la clave especificada en el **SSHServerHostKey** propiedad.<br /><br /> **Valor predeterminado:** False|  
    |Modo de autenticación de cliente|Especifica el método de autenticación que usa el puerto de envío para autenticar el cliente en el servidor SSH. Si establece en **contraseña**, debe escribir el valor en el **contraseña** propiedad. Si establece en **PublicKeyAuthentication**, debe escribir la clave privada del usuario en el **PrivateKey** propiedad. Si establece en **MultiFactorAuthentication** debe proporcionar **nombre de usuario** con su **contraseña** y **PrivateKey**. Además, si la clave privada está protegida por una contraseña, escriba la contraseña, así como para la **PrivateKeyPassword** propiedad.<br /><br /> **Valor predeterminado:** contraseña|  
    |Cifrado | Disponible a partir de BizTalk Server 2013 R2.<br/><br/>Especifique el tipo de cifrado.<br/><br/>Opciones de BizTalk Server 2013 R2: Auto, AES y TripleDES<br/><br/>Opciones de BizTalk Server 2016: automática, AES, Arcfour, Blowfish, TripleDES y DES|  
    |Contraseña|Especifique la contraseña de usuario SFTP si ha definido la **ClientAuthenticationMode** a **contraseña**.|  
    |Clave privada|Especifique la clave privada para el usuario SFTP si ha definido la **ClientAuthenticationMode** a **PublicKeyAuthentication**.|  
    |Contraseña de clave privada|Especifique una contraseña de clave privada, si es necesario para la clave especificada en el **PrivateKey** propiedad.|  
    |Servidor SSH hospedar clave huella dactilar|Especifica la huella digital del servidor utilizado por el adaptador para autenticar el servidor si la **AccessAnySSHServerHostKey** propiedad está establecida en **False**. Si las huellas digitales no coinciden, la conexión fallará.|  
    |Nombre de usuario|Especifica un nombre de usuario para el servidor FTP seguro.|  
    
    **SSH Server**
    
    |Use|Para|  
    |--------------|----------------|  
    |Anexar si existe|Si el archivo que se va a transferir al servidor FTP seguro ya existe en el destino, esta propiedad especifica si los datos del archivo que se va a transferir deben anexarse al archivo existente. Si establece en **True**, se anexan los datos. Si establece en **False**, se sobrescribe el archivo en el servidor de destino.<br /><br /> **Valor predeterminado:** False|  
    |Ruta de acceso de carpeta|Especifica la ruta de la carpeta en el servidor de FTP seguro en la que se copia el archivo.|  
    |Puerto|Especifica la dirección del puerto del servidor FTP seguro en el que tiene lugar la transferencia del archivo.|  
    |Dirección del servidor|Especifica el nombre de servidor o la dirección IP del servidor FTP seguro.|  
    |Nombre de archivo de destino|Especifica el nombre con el que el archivo se transfiere al servidor FTP seguro. También puede usar macros para el nombre de archivo de destino.|  
  
4.  Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  
  
## <a name="use-a-newer-winscp-version"></a>Usar una versión más reciente de WinSCP

Para usar una versión más reciente de WinSCP con BizTalk Server, agregue una redirección de ensamblados para que BizTalk sepa qué ensamblado cargar. La redirección se configura en los archivos de configuración de BizTalk Server: BTSNTSVC.exe.config (instancias de host de 32 bits) y BTSNTSVC64.exe.config (instancias de host de 64 bits).

A continuación incluye sintaxis de configuración de ejemplo. No olvide reemplazar `%NEWVERSION%` con su versión:

```
<configuration>
 <runtime>
  <assemblyBinding>
   <dependentAssembly>
    <assemblyIdentity name="WinSCPnet" publicKeyToken="2271ec4a3c56d0bf" culture="neutral" />
    <bindingRedirect oldVersion="1.2.10.6257" newVersion="%NEWVERSION%"/>
   </dependentAssembly>
  </assemblyBinding>
 </runtime>
</configuration>
```

Cuando termine, la configuración tiene un aspecto similar al siguiente:  

![Redirección de ensamblado en el archivo de configuración.](media/AssemblyRedirect.png)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes  
  
|Pregunta|Respuesta|  
|--------------|------------|  
|¿Qué servidores SFTP son compatibles?|Vea [servidores SFTP compatibles](http://social.technet.microsoft.com/wiki/contents/articles/29940.biztalk-serverbiztalk-services-supported-sftp-servers.aspx). A partir de BizTalk Server 2016, el adaptador SFTP utiliza WinSCP para conectarse a SFTP. Como resultado, los servidores SFTP compatibles con WinSCP deberían funcionar.|  
|¿Se puede usar el adaptador SFTP con el método de autenticación mutua (clave pública y contraseña)?|-Comenzando por **BizTalk Server 2013 R2**, sí. Si establece en **MultiFactorAuthentication** debe proporcionar **nombre de usuario** con su **contraseña** y **PrivateKey**. Además, si la clave privada está protegida por una contraseña, especifique la contraseña, así como para la **PrivateKeyPassword** propiedad.<br /><br /> -Para **BizTalk Server 2013**, ya sea **contraseña** o **PublicKeyAuthentication** puede utilizarse. **MultiFactorAuthentication** no se admite en el adaptador SFTP incluido con BizTalk Server 2013.|  
|¿Qué formatos de clave privada se admiten? ¿Se puede usar el formato de clave privada OpenSSH?|El adaptador SFTP admite únicamente el formato de archivo de clave privada PuTTY. También se puede usar PuTTYgen para convertir de OpenSSH al formato .ppk.|  
|Para SSHServerHostKeyFingerPrint, ¿qué formato y algoritmo de huella digital deben usarse?|Debe usar la huella digital MD5 de la clave del servidor en el formato: `ssh-rsa 2048 90:e4:9b:67:d9:22:a7:5f:6f:33:db:6a:b1:23:96:12`.|  
|¿Admite el adaptador SFTP el cifrado de 256 bits?|Sí, el adaptador SFTP admite el cifrado de 256 bits. Los algoritmos de cifrado admitidos son:<br /><br /> -El cifrado AES: SDCTR o CBC de 256 bits, 192 bits o 128 bits<br /><br /> -El cifrado 3DES (Triple DES): SDCTR o CBC de 168 bits|  
|¿Qué versiones SSH admite el adaptador?|Sólo SSH2. No se puede establecer conexión con los servidores SFTP con la versión SSH1.|  
|¿La máscara del archivo distingue mayúsculas de minúsculas?|No. \*.txt y \*.TXT funciona igual. Instale la actualización acumulativa más reciente de BizTalk Server 2013. Versión de BizTalk Server 2013 RTM tenía máscaras de archivo que distinguen mayúsculas y minúsculas.|  
|Exportar enlaces da un campo de contraseña en blanco. ¿Al intentar crear una ubicación de recepción al importar estos enlaces qué cambios se realizarán?|Editar el archivo de enlace editando el campo de contraseña. Además, en `<Password vt="1">MySecretPassword</Password>`, **vt = "1"** indica un valor null. Cámbielo a **vt = "8"**, lo que indica una cadena. Por ejemplo:<br /><br /> `<Password vt="8">MySecretPassword</Password>`<br /><br /> Para obtener más información, vea [http://msdn.microsoft.com/library/system.runtime.interopservices.varenum(v=vs.100).aspx](http://msdn.microsoft.com/library/system.runtime.interopservices.varenum\(v=vs.100\).aspx)|  
|¿Cómo se pueden especificar las rutas de acceso de archivo?|Normalmente, se especifican las rutas de acceso en el formato `/folder/pathname`. Sin embargo, los distintos servidores requieren diferentes formatos, con o sin barras iniciales o finales. Por lo tanto, también puede intentar lo siguiente:<br /><br /> -                   `/folder/pathname`<br /><br /> -                   `/folder/pathname/`<br /><br /> -                   `folder/pathname`<br /><br /> -                   `folder/pathname/`|  
  

