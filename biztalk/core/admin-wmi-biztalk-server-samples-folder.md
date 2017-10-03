---
title: "WMI de administración (carpeta de ejemplos de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administering, WMI
- examples, Windows Management Instrumentation (WMI)
- Windows Management Instrumentation (WMI), administering
- Windows Management Instrumentation (WMI), examples
- examples, administering
- administering, examples
ms.assetid: 39e2a6fe-2781-4be2-a152-f5e9960a0faa
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19a8698bbe916d86909005ff77c9b1eeea11604f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="admin-wmi-biztalk-server-samples-folder"></a><span data-ttu-id="f8950-102">WMI de administración (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="f8950-102">Admin-WMI (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="f8950-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye varios ejemplos de administración de Instrumental de administración de Microsoft Windows (WMI) en su kit de desarrollo de software (SDK).</span><span class="sxs-lookup"><span data-stu-id="f8950-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several Microsoft Windows Management Instrumentation (WMI) administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="f8950-104">En esta sección se proporciona información detallada acerca de la funcionalidad que se muestra en cada ejemplo de administración de WMI, de las instrucciones para la generación y ejecución del ejemplo y de los resultados que se pueden esperar.</span><span class="sxs-lookup"><span data-stu-id="f8950-104">This section provides detailed information about the functionality demonstrated by each WMI administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f8950-105">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="f8950-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="f8950-106">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="f8950-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8950-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f8950-107">In This Section</span></span>  
  
-   <span data-ttu-id="f8950-108">[Habilitar (ejemplo de BizTalk Server) de la ubicación de recepción](../core/enable-receive-location-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-108">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-109">Muestra cómo habilitar una ubicación de recepción y establecer la dirección URL de transporte de entrada para esa ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f8950-109">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
-   <span data-ttu-id="f8950-110">[Dar de alta una orquestación (ejemplo de BizTalk Server)](../core/enlist-orchestration-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-110">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-111">Muestra cómo dar de alta una orquestación de BizTalk Server en un host.</span><span class="sxs-lookup"><span data-stu-id="f8950-111">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
-   <span data-ttu-id="f8950-112">[Enumerar (ejemplo de BizTalk Server) de ubicaciones de recepción](../core/enumerate-receive-locations-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-112">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-113">Muestra cómo recuperar detalles sobre una o varias ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="f8950-113">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
-   <span data-ttu-id="f8950-114">[Quitar (ejemplo de BizTalk Server) del puerto de recepción](../core/remove-receive-port-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-114">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-115">Muestra cómo quitar uno o varios puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="f8950-115">Demonstrates how to remove one or more receive ports.</span></span>  
  
-   <span data-ttu-id="f8950-116">[Quitar puerto de envío (ejemplo de BizTalk Server)](../core/remove-send-port-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-116">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-117">Muestra cómo dar de baja y quitar uno o varios puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="f8950-117">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
-   <span data-ttu-id="f8950-118">[Establecer la propiedad de controlador de envío (ejemplo de BizTalk Server)](../core/set-send-handler-property-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-118">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-119">Muestra cómo establecer la información de configuración de XML para un controlador de envío del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="f8950-119">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
-   <span data-ttu-id="f8950-120">[Iniciar puerto de envío (ejemplo de BizTalk Server)](../core/start-send-port-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-120">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-121">Muestra cómo iniciar un puerto de envío y establecer la dirección de transporte principal al usar el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="f8950-121">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
-   <span data-ttu-id="f8950-122">[Detener la orquestación (ejemplo de BizTalk Server)](../core/stop-orchestration-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f8950-122">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="f8950-123">Muestra cómo detener una orquestación de BizTalk Server y, de forma opcional, darla de baja.</span><span class="sxs-lookup"><span data-stu-id="f8950-123">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>