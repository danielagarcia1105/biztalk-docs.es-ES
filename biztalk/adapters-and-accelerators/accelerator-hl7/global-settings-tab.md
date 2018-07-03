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
# <a name="global-settings-tab"></a><span data-ttu-id="78945-102">Ficha Configuración global</span><span class="sxs-lookup"><span data-stu-id="78945-102">Global Settings Tab</span></span>
<span data-ttu-id="78945-103">Usa el **configuración Global** tab para configurar el almacén de registro utilizado por [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78945-103">You use the **Global Settings** tab to configure the logging store used by [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  

 <span data-ttu-id="78945-104">En el **Explorador de configuración de BTAHL7** cuadro de diálogo el **configuración Global** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78945-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Global Settings** tab, do the following:</span></span>  


|     <span data-ttu-id="78945-105">Use</span><span class="sxs-lookup"><span data-stu-id="78945-105">Use this</span></span>      |                                                                                                                                                <span data-ttu-id="78945-106">Para</span><span class="sxs-lookup"><span data-stu-id="78945-106">To do this</span></span>                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      <span data-ttu-id="78945-107">**WMI**</span><span class="sxs-lookup"><span data-stu-id="78945-107">**WMI**</span></span>      |                                                                 <span data-ttu-id="78945-108">Seleccione esta opción si desea generar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] notificaciones Management Instrumentation (WMI) para BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="78945-108">Select this option if you want to generate [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) notifications for BTAHL7.</span></span>                                                                  |
|      <span data-ttu-id="78945-109">**SQL**</span><span class="sxs-lookup"><span data-stu-id="78945-109">**SQL**</span></span>      | <span data-ttu-id="78945-110">Seleccione esta opción si desea usar Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] como almacén de registro de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="78945-110">Select this option if you want to use Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your logging store for BTAHL7.</span></span> <span data-ttu-id="78945-111">**Nota:** BTAHL7 crea automáticamente las tablas necesarias para el registro si no existen.</span><span class="sxs-lookup"><span data-stu-id="78945-111">**Note:**  BTAHL7 automatically creates the tables required for logging if they do not exist.</span></span> |
|  <span data-ttu-id="78945-112">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="78945-112">**SQL Server**</span></span>   |            <span data-ttu-id="78945-113">Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre.</span><span class="sxs-lookup"><span data-stu-id="78945-113">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="78945-114">Esto es necesario cuando se selecciona el **SQL** opción.</span><span class="sxs-lookup"><span data-stu-id="78945-114">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="78945-115">La longitud máxima permitida es de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="78945-115">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="78945-116">El nombre de servidor y base de datos predeterminada es la base de datos de BTAHL7 configurada.</span><span class="sxs-lookup"><span data-stu-id="78945-116">The default server and database name is the configured BTAHL7 database.</span></span>            |
| <span data-ttu-id="78945-117">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="78945-117">**Database name**</span></span> |                                                 <span data-ttu-id="78945-118">Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="78945-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="78945-119">Esto es necesario cuando se selecciona el **SQL** opción.</span><span class="sxs-lookup"><span data-stu-id="78945-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="78945-120">La longitud máxima permitida es de 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="78945-120">The maximum allowed length is 128 characters.</span></span>                                                 |
|   <span data-ttu-id="78945-121">**Registro de eventos**</span><span class="sxs-lookup"><span data-stu-id="78945-121">**Event Log**</span></span>   |                <span data-ttu-id="78945-122">Seleccione esta opción si desea usar el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos como almacén de registro de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="78945-122">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as the logging store for BTAHL7.</span></span> <span data-ttu-id="78945-123">Usa el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para ver los mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="78945-123">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>                 |

