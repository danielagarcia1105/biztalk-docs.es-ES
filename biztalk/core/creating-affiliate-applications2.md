---
title: Crear aplicaciones afiliadas aplicaciones 2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, creating tickets
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- affiliate applications, creating
- SSO tickets
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f39fbbfb62a9081937891b98e2b01a5e7f046e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a>Crear aplicaciones afiliadas
En los pasos siguientes se indica cómo comenzar a utilizar aplicaciones afiliadas y el Inicio de sesión único (SSO).  
  
> [!NOTE]
>  Si recibe errores de SSO, compruebe que se ha utilizado una cuenta de dominio en la configuración de BizTalk Server, ya que puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
### <a name="to-create-an-affiliate-application"></a>Para crear una aplicación afiliada  
  
1.  En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.  
  
2.  En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.  
  
     Por ejemplo:  
  
     **C:\Program programa\Archivos comunes\enterprise Single Sign-On >**  
  
3.  Utilice los comandos del Inicio de sesión único empresarial. Para obtener una lista de comandos, utilice la **-ayuda** cambiar.  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     donde:  
  
    -   C:\SSOtest es la carpeta que contiene la aplicación XML.  
  
    -   El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.  
  
     Por ejemplo:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="PeopleSoftApp">  
              <description>PeopleSoft SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
             <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
              <!—-an existing group on the domain controller - >   
              <appAdminAccount>DomainName\AppAdminGroup<appAdminAccount>   
              <!-- an existing account in the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a>Crear vales de inicio de sesión único  
  
#### <a name="to-create-sso-tickets"></a>Para crear vales SSO  
  
1.  Escriba el comando siguiente para controlar el comportamiento del vale SSO:  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  Responda a las preguntas:  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     Una vez completada, recibirá una confirmación:  
  
     **Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**  
  
## <a name="enabling-the-affiliate-application-xml"></a>Habilitar el archivo XML de aplicación afiliada.  
  
#### <a name="to-enable-affiliate-application-xml"></a>Para habilitar un archivo XML de aplicación afiliada  
  
1.  Escriba el siguiente comando:  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:  
  
     `ssoclient.exe –listapps`  
  
     Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización.  
  
     **Aplicaciones disponibles para IBI\YourID - PeopleSoftApp**  
  
3.  Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  Escriba el nombre de usuario y la contraseña en los cuadros. Escriba las credenciales de inicio de sesión para la aplicación afiliada PeopleSoftApp.  
  
     Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.  
  
    -   **Id. de usuario:**`user`  
  
    -   **Contraseña:**`******`  
  
    -   **¿Confirmar? Contraseña:**`******`  
  
5.  La aplicación afiliada aparecerá en el cuadro de diálogo Adaptador BizTalk para PeopleSoft Enterprise Transport Properties.  
  
## <a name="see-also"></a>Vea también  
 [Mediante el inicio de sesión único](../core/using-single-sign-on2.md)