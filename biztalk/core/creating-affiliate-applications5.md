---
title: Crear aplicaciones afiliadas para TIBCO EMS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce5df15794886f9177f12f2a9e9a33e3ffdc335f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015291"
---
# <a name="create-affiliate-applications"></a>Crear aplicaciones afiliadas
En los pasos siguientes se describe cómo comenzar a usar aplicaciones afiliadas y el Inicio de sesión único (SSO).  
  
> [!NOTE]
>  Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server; esto puede afectar al funcionamiento del servicio SSO empresarial. SSO solo funciona con una cuenta de dominio.  
  
## <a name="create-an-affiliate-application"></a>Crear una aplicación afiliada  
  
1.  En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.  
  
2.  En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.  
  
     Por ejemplo:  
  
     **C:\Program programa\Archivos comunes\enterprise Single Sign-On >**  
  
3.  Utilice los comandos del Inicio de sesión único empresarial. Para obtener una lista de comandos, utilice la **-ayuda** cambiar.  
  
4.  Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     donde:  
  
    -   C:\SSOtest es la carpeta que contiene la aplicación XML.  
  
    -   El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.  
  
     Por ejemplo:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO EMS App">  
            <description>TIBCO EMS SSO Application</description>  
            <contact>someone@example.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
            <!—an existing group on the domain controller - >   
            <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
            <!-- an existing account in the domain group - >   
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
    </SSO>  
    ```  
  
 Mediante el uso del XML de ejemplo, la aplicación afiliada, TIBCO EMS App, contiene los valores mostrados en el indicador de comandos.  
  
## <a name="create-single-sign-on-tickets"></a>Crear vales de inicio de sesión único  
  
1.  Escriba el comando siguiente para controlar el comportamiento del vale SSO:  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  Responda a las preguntas:  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     Una vez completada, recibirá una confirmación:  
  
     **Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**  
  
## <a name="enable-affiliate-application-xml"></a>Habilitar la aplicación afiliada de XML  
  
1.  Escriba el siguiente comando:  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:  
  
     `ssoclient.exe –listapps`  
  
     Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización:  
  
     **Aplicaciones disponibles para IBI\YourID - TIBCO EMSApp**  
  
3.  Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  Escriba el nombre de usuario y la contraseña en los cuadros. Escriba las credenciales de inicio de sesión para la aplicación afiliada TIBCO EMS App.  
  
     Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.  
  
    -   Id. de usuario: **usuario**  
  
    -   Contraseña:`******`  
  
    -   Confirmar? Contraseña:`******`  
  
     La aplicación afiliada aparecerá en el adaptador de BizTalk para TIBCO EMS **propiedades de transporte** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
[Proteger el adaptador](../core/security-in-biztalk-adapter-for-tibco-ems.md)