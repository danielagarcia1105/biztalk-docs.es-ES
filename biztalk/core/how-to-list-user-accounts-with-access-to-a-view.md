---
title: Cómo enumerar los usuarios de cuentas con acceso a una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e27f1f48846c1eb134c2ee71bf9c00c72d4a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981709"
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a>Cómo enumerar cuentas de usuario con acceso a una vista
Los administradores utilizan el **get-accounts** comando de la utilidad de administración de BAM para obtener una lista de todas las cuentas de usuario para un rol de vista, lo que significa que todas las cuentas de usuario con acceso a la vista especificada.  
  
 Para obtener información acerca de cómo ver las vistas de BAM, consulte [cómo enumerar vistas de BAM](../core/how-to-list-bam-views.md).  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a>Para enumerar cuentas de usuario con acceso a una vista  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
3. Tipo **bm get-accounts-View:\<nombre de la vista\>**.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)