---
title: Cómo eliminar una aplicación afiliada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97315d21e3793ec6a282deb5f8cdd69d79ab7491
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003325"
---
# <a name="how-to-delete-an-affiliate-application"></a>Cómo eliminar una aplicación afiliada
Puede utilizar el Complemento MMC o la línea de comandos para eliminar la aplicación afiliada de la base de datos de SSO.  
  
> [!IMPORTANT]
>  Cuando se elimina una aplicación afiliada, el sistema SSO elimina automáticamente todas las asignaciones asociadas a dicha aplicación.  
  
> [!IMPORTANT]
>  Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>Para eliminar una aplicación afiliada con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento de MMC, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **eliminar**.  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>Para eliminar una aplicación afiliada con la línea de comandos  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssomanage-deleteapp *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea quitar de la Base de datos SSO.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)