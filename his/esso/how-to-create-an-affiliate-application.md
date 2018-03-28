---
title: Cómo crear una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3be483f8-2617-459e-9081-aab886c75d93
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5145111b2c585edab92cc10c3e3614e8bb91a85d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-create-an-affiliate-application"></a>Cómo crear una aplicación afiliada
Puede usar el complemento MMC o la **createapps** comando para crear una o varias aplicaciones, tal y como especifica el archivo XML. El siguiente es un archivo XML de ejemplo para Windows-Initiated Single Sign-On (SSO):  
  
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
  
-   Nombre de la aplicación afiliada.  
  
-   Campos asociados a la aplicación afiliada.  
  
-   Afiliada de tipo de aplicación (almacén de configuración, individual, grupo de host).  
  
-   Cuenta de administración igual al grupo de administradores afiliados. (Si especifica esta marca siempre usará el grupo de administradores afiliados como la cuenta de administrador para la aplicación afiliada.)  
  
> [!IMPORTANT]
>  Puede utilizar cuentas locales para la cuenta de administración y de usuario al establecer en Sí la marca allowLocalAccounts. Sin embargo, esta marca se debe utilizar sólo en escenarios de un sólo equipo.  
  
> [!IMPORTANT]
>  Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.  
  
> [!NOTE]
>  Si va a realizar la configuración en un controlador de dominio y los grupos de ámbito Local de dominio se especifican para los administradores de aplicaciones o usuarios de la aplicación al crear aplicaciones afiliadas, se recomienda que habilite la marca de la cuenta local. Para hacerlo:  
  
-   En el complemento de MMC, seleccione Permitir cuentas locales para cuentas de acceso durante el proceso de creación.  
  
-   Desde la línea de comandos, especifique allowLocalAccounts = sí en el archivo XML para la creación de la aplicación afiliada.  
  
 Después de crear esta aplicación afiliada, debe habilitarla. Para obtener más información, consulte [cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md).  
  
### <a name="to-create-an-affiliate-application-using-the-microsoft-management-console-mmc-snap-in"></a>Para crear una aplicación afiliada con el complemento de Microsoft Management Console (MMC)  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **aplicaciones afiliadas**y, a continuación, haga clic en **nuevo**.  
  
4.  Siga las instrucciones de la **crear nueva aplicación afiliada** asistente.  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a>Para crear una aplicación afiliada con la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –createapps <application file name>`, donde  *\<nombre de archivo de aplicación >* es el archivo XML.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md)   
 [Cómo eliminar una aplicación afiliada](../esso/how-to-delete-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../esso/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../esso/managing-affiliate-applications.md)