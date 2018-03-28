---
title: Crear aplicaciones afiliadas Applications4 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets, Single Sign-On
- affiliate applications, setting credentials
- affiliate applications
- Single Sign-On, creating tickets
- SSO tickets
ms.assetid: 790fbe21-8081-4d57-803f-23014c8a3135
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87aa9be716e437e80c0e85bd9e462713e48090ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="creating-affiliate-applications"></a>Crear aplicaciones afiliadas
Los pasos siguientes describen cómo empezar a trabajar con aplicaciones afiliadas con SSO.  
  
> [!NOTE]
>  Si obtiene errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial. SSO sólo funciona con una cuenta de dominio.  
  
### <a name="to-create-an-affiliate-application"></a>Para crear una aplicación afiliada  
  
1.  En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.  
  
2.  En el símbolo del sistema, vaya al directorio de la carpeta de instalación del inicio de sesión único empresarial.  
  
     Por ejemplo:  
  
     **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
3.  Utilice los comandos del Inicio de sesión único empresarial. Para obtener una lista de comandos, utilice la **-ayuda** cambiar.  
  
4.  Para crear una aplicación afiliada usando un archivo *.XML como inicio, escriba el siguiente comando:  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     donde:  
  
    -   C:\SSOtest es la carpeta que contiene la aplicación XML.  
  
    -   El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.  
  
     Por ejemplo:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="JDEdwardsApp">  
            <description>JDEdwards SSO Application</description>  
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
  
### <a name="to-create-single-sign-on-tickets"></a>Para crear vales de inicio de sesión único  
  
1.  Escriba el comando siguiente para controlar el comportamiento del vale SSO:  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  Responda a las preguntas siguientes como se muestra:  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     Cuando haya terminado, recibirá el siguiente mensaje de confirmación:  
  
     **Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**  
  
### <a name="to-enable-affiliate-application-xml"></a>Para habilitar un archivo XML de aplicación afiliada  
  
1.  Escriba el siguiente comando:  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:  
  
     `ssoclient.exe –listapps`  
  
     Aparecerán en una lista las aplicaciones afiliadas disponibles para su uso:  
  
     **Aplicaciones disponibles para IBI\YourID - JDEdwardsApp**  
  
3.  Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  Escriba el nombre de usuario y la contraseña en los cuadros. Escriba las credenciales de inicio de sesión para la aplicación afiliada JDEdwardsApp.  
  
     Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.  
  
    -   Id. de usuario: **usuario**  
  
    -   Contraseña: `******`  
  
    -   Confirmar? Contraseña: `******`  
  
     La aplicación afiliada aparecerá en el adaptador de BizTalk para JD Edwards EnterpriseOne **propiedades de transporte** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)