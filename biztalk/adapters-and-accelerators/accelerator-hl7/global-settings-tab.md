---
title: Ficha Configuración global | Microsoft Docs
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
ms.openlocfilehash: 5c19cfb387ba3cce61d21c467c1c91674204d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998685"
---
# <a name="global-settings-tab"></a>Ficha Configuración global
Usa el **configuración Global** tab para configurar el almacén de registro utilizado por [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].  

 En el **Explorador de configuración de BTAHL7** cuadro de diálogo el **configuración Global** ficha, realice lo siguiente:  


|     Use      |                                                                                                                                                Para                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **WMI**      |                                                                 Seleccione esta opción si desea generar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] notificaciones Management Instrumentation (WMI) para BTAHL7.                                                                  |
|      **SQL**      | Seleccione esta opción si desea usar Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] como almacén de registro de BTAHL7. **Nota:** BTAHL7 crea automáticamente las tablas necesarias para el registro si no existen. |
|  **SQL Server**   |            Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre. Esto es necesario cuando se selecciona el **SQL** opción. La longitud máxima permitida es de 64 caracteres.<br /><br /> El nombre de servidor y base de datos predeterminada es la base de datos de BTAHL7 configurada.            |
| **Nombre de la base de datos** |                                                 Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre de base de datos. Esto es necesario cuando se selecciona el **SQL** opción. La longitud máxima permitida es de 128 caracteres.                                                 |
|   **Registro de eventos**   |                Seleccione esta opción si desea usar el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos como almacén de registro de BTAHL7. Usa el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para ver los mensajes de eventos.                 |

