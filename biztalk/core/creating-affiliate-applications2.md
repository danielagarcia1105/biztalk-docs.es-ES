---
title: Crear aplicaciones afiliadas para PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a77926fa9d98606770ad2fe7715a3b0ff66ea5c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a>Crear aplicaciones afiliadas
En los pasos siguientes se indica cómo comenzar a utilizar aplicaciones afiliadas y el Inicio de sesión único (SSO).  
  
> [!NOTE]
>  Si recibe errores de SSO, compruebe que se ha utilizado una cuenta de dominio en la configuración de BizTalk Server, ya que puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="create-an-affiliate-application"></a>Crear una aplicación afiliada  
  
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
  
## <a name="create-single-sign-on-tickets"></a>Crear vales de inicio de sesión únicos  
  
1.  Escriba el comando siguiente para controlar el comportamiento del vale SSO:  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  Responda a las preguntas:  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     Una vez completada, recibirá una confirmación:  
  
     **Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**  
  
## <a name="enable-the-affiliate-application-xml"></a>Habilitar la aplicación afiliada XML  
  
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
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)