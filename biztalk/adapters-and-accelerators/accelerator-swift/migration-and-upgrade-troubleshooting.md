---
title: "Solución de problemas de actualización y migración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0e2a18b1cdba47c999150b5bc52c0b016aec61
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="migration-and-upgrade-troubleshooting"></a>Solución de problemas de actualización y migración
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a>Ensamblados deben ser implementada antes de una actualización  
  
### <a name="symptom"></a>Síntoma  
 Cuando intenta actualizar A4SWIFT, se produce un error en el proceso de actualización.  
  
### <a name="possible-cause"></a>Causa posible  
 Los siguientes ensamblados de A4SWIFT todavía se implementan cuando se realiza la actualización: Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration, Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas, Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.  
  
> [!NOTE]
>  No es necesario volver a implementar Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas. El programa de instalación vuelve a implementar ese ensamblado.  
  
### <a name="solution"></a>Solución  
 Anular la implementación manualmente los ensamblados de A4SWIFT cuatro en el orden siguiente:  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.  
  
 Después de haber actualizado, volver a implementar estos ensamblados (con **BTSTask.exe**) en el orden inverso.  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a>Una actualización quita los permisos de acceso para la carpeta del servicio  
  
### <a name="symptom"></a>Síntoma  
 Después de actualizar a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], el permiso de acceso para el Acelerador de BizTalk para SWIFT\Service carpeta %programfiles%\Microsoft es incorrecto.  
  
### <a name="possible-cause"></a>Causa posible  
 Cuando se actualiza a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], el proceso de actualización quita permisos de acceso para los grupos Administradores de A4SWIFT y los usuarios de A4SWIFT el Acelerador de BizTalk para SWIFT\Service carpeta %programfiles%\Microsoft.  
  
### <a name="solution"></a>Solución  
 Si se produce este problema, establezca manualmente los siguientes permisos de acceso para la carpeta del servicio:  
  
|Nombre de usuario o grupo|Permiso|  
|------------------------|----------------|  
|Administradores de A4SWIFT|Control total|  
|Usuarios de A4SWIFT|Leer y ejecutar|  
  
 Para establecer estos permisos, haga lo siguiente:  
  
 En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a *% programfiles %*\Microsoft Acelerador de BizTalk para SWIFT\Service.  
  
1.  Haga clic en la carpeta del servicio, haga clic en **propiedades**y, a continuación, haga clic en el **seguridad** ficha.  
  
2.  En el panel de nombres de grupo o usuario del cuadro de diálogo Propiedades del servicio, haga clic en **agregar**, escriba ***\<nombre del servidor\>* los administradores \A4SWIFT**y, a continuación, haga clic en **Aceptar** .  
  
    > [!NOTE]
    >  Si el grupo de administradores de A4SWIFT es un grupo de dominio, escriba ***\<nombre de dominio\>* \A4SWIFT administradores**.  
  
3.  Repita el paso 2 para ***\<nombre del servidor\>* \A4SWIFT usuarios**, o  **\< *nombre de dominio*\>\A4SWIFT usuarios** si el Grupo de usuarios de A4SWIFT es un grupo de dominio.  
  
4.  En el panel de nombres de usuario o grupo, seleccione **A4SWIFT administradores**. En el panel permisos, seleccione **permitir** para **Control total**.  
  
5.  En el panel de nombres de usuario o grupo, seleccione **A4SWIFT usuarios**. En el panel permisos, haga clic en **permitir** para **leer y ejecutar**, **contenido de la carpeta de lista**, y **lectura**.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas: problemas y soluciones](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)