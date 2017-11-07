---
title: Crear aplicaciones afiliadas Applications3 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 857ee7edd623332e72176ac09082f0ec9fc460f4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a>Crear aplicaciones afiliadas
Los pasos siguientes describen cómo empezar a usar aplicaciones afiliadas con el inicio de sesión único (SSO).  
  
> [!NOTE]
>  Si recibe errores de SSO, compruebe que usó una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio ESSO. SSO sólo funciona con una cuenta de dominio.  
  
## <a name="creating-an-affiliate-application"></a>Creación de una aplicación afiliada  
  
#### <a name="to-create-an-affiliate-application"></a>Para crear una aplicación afiliada  
  
1.  En **el Panel de Control**, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.  
  
2.  En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.  
  
     Por ejemplo:  
  
     **C:\Program programa\Archivos comunes\enterprise Single Sign-On >**  
  
3.  Utilice los comandos del Inicio de sesión único empresarial. Para obtener una lista de comandos, use el modificador -help.  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  Para crear la aplicación afiliada mediante el *. XML como un principio, escriba el comando siguiente:  
  
     **ssomanage.exe - createapps C:\SSOtest\AffiliateApplication.xml**  
  
     donde:  
  
     C:\SSOtest es la carpeta que contiene el XML de la aplicación.  
  
     El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.  
  
     Por ejemplo:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="JDEdwardsApp">  
              <description>JDEdwards SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
              <userGroup>ibi\Domain Users</userGroup>  
              <!—-an existing group on the domain controller - >   
              <appAdminGroup>ibi\YourID</appAdminGroup>  
              <!-- an existing account within the domain group - >   
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
  
     Cuando haya terminado, recibirá un mensaje de confirmación:  
  
     **Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**  
  
## <a name="enabling-the-affiliate-application-xml"></a>Habilitar el archivo XML de aplicación afiliada.  
  
#### <a name="to-enable-affiliate-application-xml"></a>Para habilitar un archivo XML de aplicación afiliada  
  
1.  Escriba el comando siguiente:  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  Escriba el siguiente comando para enumerar las aplicaciones y para comprobar que se creó la aplicación:  
  
     `ssoclient.exe –listapps`  
  
     Las aplicaciones afiliadas disponibles para usar aparecen en una lista.  
  
     **Aplicaciones disponibles para IBI\YourID - JDEdwardsApp**  
  
3.  Escriba el comando siguiente para establecer las credenciales de la aplicación afiliada:  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  Escriba el nombre de usuario y la contraseña en los cuadros. Escriba las credenciales de inicio de sesión para la aplicación afiliada JDEdwardsApp. Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.  
  
    -   **Id. de usuario:** usuario  
  
    -   **Contraseña:** ******  
  
    -   **¿Confirmar? Contraseña:** ******  
  
5.  La aplicación afiliada aparece en la lista desplegable del cuadro de diálogo Propiedades de transporte de BizTalk Adapter para JD Edwards OneWorld.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)