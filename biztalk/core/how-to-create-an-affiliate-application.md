---
title: Cómo crear una aplicación afiliada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], creating
- applications [SSO], creating
- creating, applications [SSO]
ms.assetid: d0967c4b-6201-416a-9d3a-23b5de5b83d6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8775ea82843641600c9156d79afab49e6cd7c634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003109"
---
# <a name="how-to-create-an-affiliate-application"></a>Cómo crear una aplicación afiliada
Puede utilizar el Complemento MMC o este comando para crear una o más aplicaciones, como especificó el archivo XML. Un ejemplo de un archivo XML para SSO iniciado por Windows es:  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no" configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 Tras crear una aplicación afiliada, no podrá modificar las siguientes propiedades:  
  
-   Nombre de la aplicación afiliada  
  
-   Campos asociados con la aplicación afiliada  
  
-   Tipo de aplicación afiliada (grupo de host, individual o almacén de configuración)  
  
-   Cuenta de administración igual al grupo de administradores afiliados. (Si especifica esta marca, se utilizará siempre el grupo de administradores afiliados como la cuenta de administrador para la aplicación afiliada)  
  
> [!IMPORTANT]
>  Puede utilizar cuentas locales para la cuenta de administración y de usuario al establecer en Sí la marca allowLocalAccounts. Sin embargo, esta marca se debe utilizar sólo en escenarios de un sólo equipo.  
  
> [!IMPORTANT]
>  Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.  
  
 Después de crear esta aplicación afiliada, debe habilitarla. Para obtener más información, consulte [cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md).  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a>Para crear una aplicación afiliada con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **aplicaciones afiliadas**y, a continuación, haga clic en **crear aplicación**.  
  
4.  Siga las instrucciones de la **Enterprise Single Sign-On Asistente para aplicaciones**.  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a>Para crear una aplicación afiliada con la línea de comandos  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssomanage – createapps *\<nombre de archivo de aplicación\>**<em>, donde *\<nombre de archivo de aplicación\></em>  es el archivo XML.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md)   
 [Cómo eliminar una aplicación afiliada](../core/how-to-delete-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)