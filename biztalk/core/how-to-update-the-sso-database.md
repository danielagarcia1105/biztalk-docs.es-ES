---
title: "Cómo actualizar la base de datos SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tickets [SSO], modifying
- managing [SSO], modifying Credential cache timeout
- tickets [SSO], timeouts
- modifying, SSO database
- managing [SSO], modifying ticket timeouts
- SSO database, modifying
ms.assetid: 45eb6a77-d91a-44a8-b26d-05508c288c36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1381ee4e5c2b90a96c52b59d125ec3121af02a4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-sso-database"></a>Cómo actualizar la base de datos SSO
Puede cambiar la información global de la base de datos de SSO (por ejemplo, identificación del servidor secreto principal, nombres de cuenta, auditoría de la base de datos, tiempo de espera de vales y tiempo de espera de almacenamiento de credenciales en caché) utilizando el Complemento MMC o la línea de comandos.  
  
## <a name="changing-timeouts-for-the-sso-system"></a>Cambiar los tiempos de espera del sistema de SSO  
 Puede modificar dos tiempos de espera en el nivel del sistema de inicio de sesión único (SSO) empresarial:  
  
 **Tiempo de espera de vale.** esta propiedad especifica el período de validez de un vale emitido por SSO. Para adaptarse a la mayoría de los escenarios de una empresa que utilice SSO, el tiempo de espera predeterminado del vale es de 2 minutos. El administrador de SSO puede cambiar este valor en función de los requisitos de la aplicación.  
  
 **Tiempo de espera de caché de credenciales.** Esta propiedad especifica el tiempo de espera de almacenamiento en caché de credenciales para todos los servidores de SSO. Los servidores de SSO almacenan en caché las credenciales después de la primera búsqueda. De forma predeterminada, el tiempo de espera de almacenamiento en caché de las credenciales es de 60 minutos. El administrador de SSO puede cambiar este valor por otro más apropiado según los requisitos de seguridad.  
  
 Ambos tiempos de espera pueden cambiarse actualizando la base de datos de SSO.  
  
 Un ejemplo de archivo XML para actualizar la base de datos de SSO es:  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
<secretServer>ComputerA</secretServer>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
<ticketTimeout>2</ticketTimeout>  
<credCacheTimeout>60</credCacheTimeout>  
</globalInfo>  
</sso>  
  
```  
  
#### <a name="to-change-timeouts-using-the-mmc-snap-in"></a>Para cambiar los tiempo de espera utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades del sistema** cuadro de diálogo, haga clic en el **General** ficha.  
  
5.  Especifique la configuración adecuada y haga clic en **Aceptar**.  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>Para actualizar la base de datos de SSO utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **Actualizar base de datos**.  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a>Para actualizar la base de datos de SSO utilizando la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage-updatedb \<archivo de actualización >**, donde  **\<archivo de actualización >** es la ruta de acceso y nombre del archivo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md)   
 [Uso de SSO](../core/using-sso.md)