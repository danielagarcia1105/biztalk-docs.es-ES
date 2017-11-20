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
ms.openlocfilehash: e15bc1f9004c79b8d87375d9fe9f6cb805e12e94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="selecting-the-logging-store"></a><span data-ttu-id="8bec9-102">Seleccionar el almacén de registro</span><span class="sxs-lookup"><span data-stu-id="8bec9-102">Selecting the Logging Store</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="8bec9-103">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] proporciona la opción para seleccionar una combinación de almacenes de registro diferentes, como [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], y [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="8bec9-103"> [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] provides you with the option to select a combination of different logging stores, such as [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log.</span></span>  
  
 <span data-ttu-id="8bec9-104">Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración para configurar el almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="8bec9-104">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to configure the logging store.</span></span>  
  
 <span data-ttu-id="8bec9-105">Utilice los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración del explorador y seleccione el almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="8bec9-105">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and select the logging store.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="8bec9-106">Para abrir el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="8bec9-106">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="8bec9-107">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="8bec9-107">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-select-the--logging-store"></a><span data-ttu-id="8bec9-108">Para seleccionar el almacén de registro</span><span class="sxs-lookup"><span data-stu-id="8bec9-108">To select the  logging store</span></span>  
  
1.  <span data-ttu-id="8bec9-109">En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración, en la **configuración Global** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bec9-109">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, on the **Global Settings** tab, do the following:</span></span>  
  
    |<span data-ttu-id="8bec9-110">Use</span><span class="sxs-lookup"><span data-stu-id="8bec9-110">Use this</span></span>|<span data-ttu-id="8bec9-111">Para</span><span class="sxs-lookup"><span data-stu-id="8bec9-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8bec9-112">**WMI**</span><span class="sxs-lookup"><span data-stu-id="8bec9-112">**WMI**</span></span>|<span data-ttu-id="8bec9-113">Seleccione esta opción si desea generar notificaciones de WMI para BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="8bec9-113">Select this option if you want to generate WMI notifications for BTAHL7.</span></span>|  
    |<span data-ttu-id="8bec9-114">**SQL**</span><span class="sxs-lookup"><span data-stu-id="8bec9-114">**SQL**</span></span>|<span data-ttu-id="8bec9-115">Seleccione esta opción si desea utilizar [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] como almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="8bec9-115">Select this option if you want to use [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your  logging store.</span></span> <span data-ttu-id="8bec9-116">**Nota:** BTAHL7 crea automáticamente las tablas necesarias para iniciar una sesión si no existen.</span><span class="sxs-lookup"><span data-stu-id="8bec9-116">**Note:**  BTAHL7 automatically creates the tables required for  logging if they do not exist.</span></span>|  
    |<span data-ttu-id="8bec9-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8bec9-117">**SQL Server**</span></span>|<span data-ttu-id="8bec9-118">Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre.</span><span class="sxs-lookup"><span data-stu-id="8bec9-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="8bec9-119">Esto es necesario cuando se selecciona el **SQL** opción.</span><span class="sxs-lookup"><span data-stu-id="8bec9-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="8bec9-120">La longitud máxima permitida es de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8bec9-120">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="8bec9-121">El nombre de servidor y base de datos predeterminada es la base de datos de BTAHL7 configurado.</span><span class="sxs-lookup"><span data-stu-id="8bec9-121">The default server and database name is the configured BTAHL7 database.</span></span>|  
    |<span data-ttu-id="8bec9-122">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="8bec9-122">**Database name**</span></span>|<span data-ttu-id="8bec9-123">Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8bec9-123">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="8bec9-124">Esto es necesario cuando se selecciona el **SQL** opción.</span><span class="sxs-lookup"><span data-stu-id="8bec9-124">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="8bec9-125">La longitud máxima permitida es de 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8bec9-125">The maximum allowed length is 128 characters.</span></span>|  
    |<span data-ttu-id="8bec9-126">**Registro de eventos**</span><span class="sxs-lookup"><span data-stu-id="8bec9-126">**Event  Log**</span></span>|<span data-ttu-id="8bec9-127">Seleccione esta opción si desea usar el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos como almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="8bec9-127">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as your  logging store.</span></span> <span data-ttu-id="8bec9-128">Usa el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para ver los mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="8bec9-128">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>|  
  
2.  <span data-ttu-id="8bec9-129">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8bec9-129">Click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bec9-130">La configuración regional de los eventos registrados por el agente de registro de eventos dependen de la configuración regional de la cuenta de servicio de registro.</span><span class="sxs-lookup"><span data-stu-id="8bec9-130">The locale of the events logged by the  Logging event broker depend on the locale of the  Logging Service account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bec9-131">Al cambiar la contraseña de la cuenta de servicio de registro, primero debe cambiar la contraseña en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsAD](../../includes/btsad-md.md)] servicio de directorio y, a continuación, reinicie el registro de servicio después de cambiar la contraseña del servicio de registro en todos los servidores ejecutan.</span><span class="sxs-lookup"><span data-stu-id="8bec9-131">When changing the  Logging Service account password, you should first change the password in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)] directory service, and then restart the  Logging Service after changing the  Logging Service password on every server running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bec9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bec9-132">See Also</span></span>  
 <span data-ttu-id="8bec9-133">[Procesamiento por lotes de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="8bec9-133">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 [<span data-ttu-id="8bec9-134">Configuración de registro</span><span class="sxs-lookup"><span data-stu-id="8bec9-134">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)