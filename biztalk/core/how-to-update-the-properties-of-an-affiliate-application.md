---
title: Cómo actualizar las propiedades de una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef4a2fb99d423f7c7ccb08cec58c3c49928e1ed
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972650"
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a>Cómo actualizar las propiedades de una aplicación afiliada
Puede utilizar el Complemento MMC o este comando para actualizar una o más propiedades de aplicaciones, como especificó el archivo XML. Deberá ser administrador afiliado para realizar esta tarea. A continuación se muestra un ejemplo de archivo XML que enumera los campos que puede actualizar.  
  
```  
<SSO>  
<application name="SSOApplication">  
<description>An SSO Application</description>  
<contact>someone@companyname.com</contact>  
<appUserAccount>DomainName\AppUserGroup</appUserAccount>  
<appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
<flags allowTickets="no" validateTickets="yes"  timeoutTickets="yes" enableApp="no" />  
</application>  
</SSO>  
  
```  
  
 Tras crear una aplicación afiliada, no podrá modificar las siguientes propiedades:  
  
-   Nombre de la aplicación afiliada  
  
-   Campos asociados con la aplicación afiliada  
  
-   Tipo de aplicación afiliada (grupo de host, individual o almacén de configuración)  
  
-   Cuenta de administración igual al grupo de administradores afiliados. (Si especifica esta marca, se utilizará siempre el grupo de administradores afiliados como la cuenta de administrador para la aplicación afiliada)  
  
> [!IMPORTANT]
>  Puede utilizar cuentas locales para la cuenta de administración y de usuario al establecer en Sí la marca allowLocalAccounts. Sin embargo, esta marca se puede utilizar sólo en escenarios de un único equipo.  
  
> [!IMPORTANT]
>  Para llevar a cabo esta tarea deberá ser administrador de SSO, administrador de aplicaciones o administrador afiliado de SSO.  
  
> [!IMPORTANT]
>  Debe ser un administrador de SSO para modificar las marcas de compras de vales (validateTickets y timeoutTickets).  
  
> [!IMPORTANT]
>  Debe ser un administrador de SSO o administrador afiliado de SSO para modificar la cuenta de administración de la aplicación.  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a>Para actualizar las propiedades de una aplicación afiliada con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **actualización**.  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a>Para actualizar las propiedades de una aplicación afiliada con la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – updateapps \<nombre de archivo de aplicación\>**, donde el nombre de archivo de aplicación es el archivo XML.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)