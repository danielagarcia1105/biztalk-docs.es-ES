---
title: Crear aplicaciones para TIBCO Rendezvous afiliadas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a286a80ef2c867dd196fcdce414f2d0ff3c8255c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a>Crear aplicaciones afiliadas
En los pasos siguientes se describe cómo comenzar a trabajar con aplicaciones afiliadas y el Inicio de sesión único (SSO). Para obtener información completa acerca de cómo usar el Inicio de sesión único de Enterprise, vea la documentación de Microsoft.  
  
> [!NOTE]
>  Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="create-an-affiliate-application"></a>Crear una aplicación afiliada  
  
1.  En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.  
  
2.  En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial. Por ejemplo:  
  
     **C:\Program programa\Archivos comunes\enterprise Single Sign-On >**  
  
3.  Utilice los comandos del Inicio de sesión único empresarial. Para obtener una lista de comandos, utilice la **-ayuda** cambiar.  
  
4.  Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     Donde:  
  
     C:\SSOtest es la carpeta que contiene la aplicación XML.  
  
     El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.  
  
     Por ejemplo:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO RendezvousApp">  
            <description> TIBCO Rendezvous SSO Application</description>  
            <contact>someone@microsoft.com</contact>  
            <userGroup>ibi\Domain Users</userGroup>  
            <!—an existing group on the domain controller - >   
            <appAdminGroup>ibi\YourID</appAdminGroup>  
            <!-- an existing account within the domain group - >   
  
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
  
        </application>  
    </SSO>  
    ```  
  
## <a name="create-single-sign-on-tickets"></a>Crear vales de inicio de sesión único  
  
1.  Escriba el comando siguiente para controlar el comportamiento del vale SSO:  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  Responda a las preguntas siguientes como se muestra:  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  Cuando haya terminado, recibirá el siguiente mensaje de confirmación:  
  
     **Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**  
  
## <a name="enable-affiliate-application-xml"></a>Habilitar la aplicación afiliada de XML  
  
1.  Escriba el siguiente comando:  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:  
  
     `ssoclient.exe –listapps`  
  
     Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización.  
  
     **Aplicaciones disponibles para IBI\YourID - TIBCO RendezvousApp**  
  
3.  Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  Escriba el nombre de usuario y contraseña en los cuadros.  
  
5.  Escriba las credenciales de inicio de sesión para la aplicación afiliada TIBCO RendezvousApp.  
  
     Por ejemplo, escriba la identificación de usuario y la contraseña para que dicho usuario obtenga acceso al sistema a través del servidor SSO.  
  
    -   Id. de usuario: usuario  
  
    -   Contraseña: ******  
  
    -   Confirmar contraseña: ******  
  
6.  La aplicación afiliada aparecerá en el adaptador de BizTalk para TIBCO Rendezvous **propiedades de transporte** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador de BizTalk para TIBCO Rendezvous](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   