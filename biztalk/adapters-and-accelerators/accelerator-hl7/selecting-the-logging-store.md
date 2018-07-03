---
title: Seleccionar el registro de Store | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 199726853eae4faf6efe67f622a8df2cbab1ccd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986037"
---
# <a name="selecting-the-logging-store"></a><span data-ttu-id="b9bd3-102">Seleccionar el registro de Store</span><span class="sxs-lookup"><span data-stu-id="b9bd3-102">Selecting the Logging Store</span></span>
<span data-ttu-id="b9bd3-103">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] le proporciona la opción para seleccionar una combinación de los almacenes de registro diferentes, como [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], y [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-103">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] provides you with the option to select a combination of different logging stores, such as [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log.</span></span>  

 <span data-ttu-id="b9bd3-104">Usa el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración para configurar el almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-104">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to configure the logging store.</span></span>  

 <span data-ttu-id="b9bd3-105">Use los procedimientos siguientes para abrir [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración y seleccione el almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-105">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and select the logging store.</span></span>  

### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="b9bd3-106">Para abrir el Explorador de configuración de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="b9bd3-106">To open BTAHL7 Configuration Explorer</span></span>  

-   <span data-ttu-id="b9bd3-107">Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-107">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

### <a name="to-select-the--logging-store"></a><span data-ttu-id="b9bd3-108">Para seleccionar el almacén de registro</span><span class="sxs-lookup"><span data-stu-id="b9bd3-108">To select the  logging store</span></span>  

1. <span data-ttu-id="b9bd3-109">En [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración, en el **configuración Global** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9bd3-109">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, on the **Global Settings** tab, do the following:</span></span>  


   |     <span data-ttu-id="b9bd3-110">Use</span><span class="sxs-lookup"><span data-stu-id="b9bd3-110">Use this</span></span>      |                                                                                                                                     <span data-ttu-id="b9bd3-111">Para</span><span class="sxs-lookup"><span data-stu-id="b9bd3-111">To do this</span></span>                                                                                                                                     |
   |-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      <span data-ttu-id="b9bd3-112">**WMI**</span><span class="sxs-lookup"><span data-stu-id="b9bd3-112">**WMI**</span></span>      |                                                                                                      <span data-ttu-id="b9bd3-113">Seleccione esta opción si desea generar notificaciones de WMI para BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-113">Select this option if you want to generate WMI notifications for BTAHL7.</span></span>                                                                                                      |
   |      <span data-ttu-id="b9bd3-114">**SQL**</span><span class="sxs-lookup"><span data-stu-id="b9bd3-114">**SQL**</span></span>      |                     <span data-ttu-id="b9bd3-115">Seleccione esta opción si desea usar [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] como almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-115">Select this option if you want to use [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your  logging store.</span></span> <span data-ttu-id="b9bd3-116">**Nota:** BTAHL7 crea automáticamente las tablas necesarias para el registro si no existen.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-116">**Note:**  BTAHL7 automatically creates the tables required for  logging if they do not exist.</span></span>                     |
   |  <span data-ttu-id="b9bd3-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b9bd3-117">**SQL Server**</span></span>   | <span data-ttu-id="b9bd3-118">Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="b9bd3-119">Esto es necesario cuando se selecciona el **SQL** opción.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="b9bd3-120">La longitud máxima permitida es de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-120">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="b9bd3-121">El nombre de servidor y base de datos predeterminada es la base de datos de BTAHL7 configurada.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-121">The default server and database name is the configured BTAHL7 database.</span></span> |
   | <span data-ttu-id="b9bd3-122">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="b9bd3-122">**Database name**</span></span> |                                      <span data-ttu-id="b9bd3-123">Tipo de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-123">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="b9bd3-124">Esto es necesario cuando se selecciona el **SQL** opción.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-124">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="b9bd3-125">La longitud máxima permitida es de 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-125">The maximum allowed length is 128 characters.</span></span>                                      |
   |  <span data-ttu-id="b9bd3-126">**Registro de eventos**</span><span class="sxs-lookup"><span data-stu-id="b9bd3-126">**Event  Log**</span></span>   |          <span data-ttu-id="b9bd3-127">Seleccione esta opción si desea usar el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos como almacén de registro.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-127">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as your  logging store.</span></span> <span data-ttu-id="b9bd3-128">Usa el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Visor de eventos para ver los mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-128">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>          |


2. <span data-ttu-id="b9bd3-129">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-129">Click **Save**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b9bd3-130">La configuración regional de los eventos registrados por el agente de registro de eventos dependen de la configuración regional de la cuenta de servicio de registro.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-130">The locale of the events logged by the  Logging event broker depend on the locale of the  Logging Service account.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="b9bd3-131">Al cambiar la contraseña de cuenta de servicio de registro, primero debe cambiar la contraseña en Microsoft [!INCLUDE[btsAD](../../includes/btsad-md.md)] servicio de directorio y, a continuación, reinicie el registro del servicio después de cambiar la contraseña del servicio de registro en cada servidor ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b9bd3-131">When changing the  Logging Service account password, you should first change the password in Microsoft [!INCLUDE[btsAD](../../includes/btsad-md.md)] directory service, and then restart the  Logging Service after changing the  Logging Service password on every server running it.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b9bd3-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9bd3-132">See Also</span></span>  
 <span data-ttu-id="b9bd3-133">[Mensaje de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="b9bd3-133">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 [<span data-ttu-id="b9bd3-134">Configuración del registro</span><span class="sxs-lookup"><span data-stu-id="b9bd3-134">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)