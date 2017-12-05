---
title: "Seleccionar el almacén de registro | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0518b536db16d641b77a61cfeb4851990a7bca0a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="selecting-the-logging-store"></a>Seleccionar el almacén de registro
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] proporciona la opción para seleccionar una combinación de almacenes de registro diferentes, como [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], y [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos.  
  
 Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración para configurar el almacén de registro.  
  
 Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración del explorador y seleccione el almacén de registro.  
  
### <a name="to-open-btahl7-configuration-explorer"></a>Para abrir el Explorador de configuración de BTAHL7  
  
-   Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
### <a name="to-select-the--logging-store"></a>Para seleccionar el almacén de registro  
  
1.  En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración, en la **configuración Global** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**WMI**|Seleccione esta opción si desea generar notificaciones de WMI para BTAHL7.|  
    |**SQL**|Seleccione esta opción si desea utilizar [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] como almacén de registro. **Nota:** BTAHL7 crea automáticamente las tablas necesarias para iniciar una sesión si no existen.|  
    |**SQL Server**|Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre. Esto es necesario cuando se selecciona el **SQL** opción. La longitud máxima permitida es de 64 caracteres.<br /><br /> El nombre de servidor y base de datos predeterminada es la base de datos de BTAHL7 configurado.|  
    |**Nombre de la base de datos**|Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre de base de datos. Esto es necesario cuando se selecciona el **SQL** opción. La longitud máxima permitida es de 128 caracteres.|  
    |**Registro de eventos**|Seleccione esta opción si desea usar el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos como almacén de registro. Usa el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para ver los mensajes de eventos.|  
  
2.  Haga clic en **Guardar**.  
  
    > [!NOTE]
    >  La configuración regional de los eventos registrados por el agente de registro de eventos dependen de la configuración regional de la cuenta de servicio de registro.  
  
    > [!NOTE]
    >  Al cambiar la contraseña de la cuenta de servicio de registro, primero debe cambiar la contraseña en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsAD](../../includes/btsad-md.md)] servicio de directorio y, a continuación, reinicie el registro de servicio después de cambiar la contraseña del servicio de registro en todos los servidores ejecutan.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [Configuración del registro](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)