---
title: Ficha Configuración global | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.globalsettings
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- Global Settings tab [Configuration Explorer]
- auditing, configuring
ms.assetid: 057189f7-9072-4841-950f-371ba1f73a15
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 022ad14cc93b55c7ad928c06358f2714531b40b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204900"
---
# <a name="global-settings-tab"></a>Ficha Configuración global
Usa el **configuración Global** ficha para configurar el almacén de registro utilizado por [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].  
  
 En el **Explorador de configuración de BTAHL7** cuadro de diálogo, en la **configuración Global** ficha, realice lo siguiente:  
  
|Use|Para|  
|--------------|----------------|  
|**WMI**|Seleccione esta opción si desea generar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] notificaciones Management Instrumentation (WMI) para BTAHL7.|  
|**SQL**|Seleccione esta opción si desea usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] como almacén de registro para BTAHL7. **Nota:** BTAHL7 crea automáticamente las tablas necesarias para iniciar una sesión si no existen.|  
|**SQL Server**|Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre. Esto es necesario cuando se selecciona el **SQL** opción. La longitud máxima permitida es de 64 caracteres.<br /><br /> El nombre de servidor y base de datos predeterminada es la base de datos de BTAHL7 configurado.|  
|**Nombre de la base de datos**|Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre de base de datos. Esto es necesario cuando se selecciona el **SQL** opción. La longitud máxima permitida es de 128 caracteres.|  
|**Registro de eventos**|Seleccione esta opción si desea usar el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos como el almacén de registro de BTAHL7. Usa el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para ver los mensajes de eventos.|