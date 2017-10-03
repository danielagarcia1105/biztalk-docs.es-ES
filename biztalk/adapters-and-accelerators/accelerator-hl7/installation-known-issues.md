---
title: "Problemas conocidos de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4e9197d2b3c448b4fd9cc42c0cdeb929917061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installation-known-issues"></a>Problemas conocidos de instalación
Información útil que puede ayudar a evitar problemas de instalación.  
  
## <a name="prerequisites-for-installing-btahl7"></a>Requisitos previos para la instalación de BTAHL7  
 Los requisitos previos para la instalación de [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] incluyen lo siguiente:  
  
-   Componentes básicos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], incluido el inicio de sesión único (SSO) empresarial, grupo y en tiempo de ejecución, debe configurarse.  
  
-   El usuario de instalación y configuración de BTAHL7 debe ser un miembro del grupo Administradores de BizTalk y un miembro del grupo Administradores en el servidor de SQL Server donde se almacenan los datos de BTAHL7.
  
## <a name="sql-server-mixed-mode-not-supported"></a>Modo mixto de SQL Server no admitido  
El [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] no es compatible con SQL Server en modo mixto.  
  
## <a name="repair-does-not-work-from-uninstallchange"></a>La reparación no funciona desde desinstalar o cambiar  
Si está habilitado el control de acceso de usuario (UAC), e intenta reparar la instalación mediante el panel de control, se produce un error en la reparación. 

Microsoft recomienda que mantener habilitado UAC.

 **Resolución**  
  
 Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe y, a continuación, seleccione **reparación**.  
  
## <a name="see-also"></a>Vea también  
[Instalar o actualizar Acelerador de Microsoft BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)