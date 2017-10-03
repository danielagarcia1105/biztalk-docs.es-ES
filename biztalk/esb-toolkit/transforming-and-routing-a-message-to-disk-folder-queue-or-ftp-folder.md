---
title: Transformar y enrutar un mensaje a la carpeta de disco, la cola o la carpeta FTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eb767b588f5531e033ec0c867ee2c6dfad02bc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a><span data-ttu-id="2827f-102">Transformar y enrutar un mensaje a la carpeta de disco, la cola o la carpeta FTP</span><span class="sxs-lookup"><span data-stu-id="2827f-102">Transforming and Routing a Message to Disk Folder, Queue, or FTP Folder</span></span>
<span data-ttu-id="2827f-103">En este caso de uso, ESB transforma un mensaje enviado a través del servicio Web de itinerario o cualquier en rampa.</span><span class="sxs-lookup"><span data-stu-id="2827f-103">In this use case, the ESB transforms a message submitted through the Itinerary Web service or any on-ramp.</span></span> <span data-ttu-id="2827f-104">Búsqueda de resolución dinámica de tipo FILE, FTP o ubicación de la cola determina el nombre de asignación (para la transformación) y el extremo de destino para el mensaje, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="2827f-104">A dynamic resolution lookup of type FILE, FTP, or queue location determines the map name (for transformation) and the target endpoint for the message, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="2827f-105">![Transformación de carpeta de disco](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span><span class="sxs-lookup"><span data-stu-id="2827f-105">![Transforming Disk Folder](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")</span></span>  
  
 <span data-ttu-id="2827f-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="2827f-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="2827f-107">**Transformar y enrutar un mensaje a una carpeta del disco**</span><span class="sxs-lookup"><span data-stu-id="2827f-107">**Transforming and routing a message to a disk folder**</span></span>  
  
 <span data-ttu-id="2827f-108">El ejemplo de resolución dinámica que se incluye con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="2827f-108">The Dynamic Resolution sample included with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="2827f-109">Muestra cómo utilizar los componentes para resolver la ubicación del extremo dinámicamente, establecer las propiedades de enrutamientos y resolver y ejecutar [!INCLUDE[prague](../includes/prague-md.md)] se asigna en el nivel de mensajería, sin utilizar una orquestación.</span><span class="sxs-lookup"><span data-stu-id="2827f-109">It shows how to use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute [!INCLUDE[prague](../includes/prague-md.md)] maps at the messaging level, without using an orchestration.</span></span> <span data-ttu-id="2827f-110">También muestra los patrones de mensajería unidireccionales y bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="2827f-110">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
 <span data-ttu-id="2827f-111">Una extensión de este caso de uso es una solución sencilla de enrutamiento que enruta un mensaje entrante a un archivo, FTP o ubicación de la cola sin el paso adicional de transformación.</span><span class="sxs-lookup"><span data-stu-id="2827f-111">An extension of this use case is a simple routing solution that routes an incoming message to a file, FTP, or queue location without the additional step of transformation.</span></span>  
  
 <span data-ttu-id="2827f-112">Para obtener más información, consulte [instalar y ejecutar el ejemplo de resolución dinámicos](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span><span class="sxs-lookup"><span data-stu-id="2827f-112">For more information, see [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>