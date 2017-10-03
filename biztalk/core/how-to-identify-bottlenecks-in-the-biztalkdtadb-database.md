---
title: "Cómo identificar cuellos de botella en la base de datos BizTalkDTADb | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4499bc3-d50b-4b97-b19c-93c7bcc40483
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c7463a0288733936189d3cbbb69b59b3b202419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-biztalkdtadb-database"></a><span data-ttu-id="0af83-102">Cómo identificar cuellos de botella en la base de datos BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="0af83-102">How to Identify Bottlenecks in the BizTalkDTADb Database</span></span>
<span data-ttu-id="0af83-103">Para identificar cuellos de botella en la base de datos BizTalkDTADb, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0af83-103">To identify bottlenecks in the BizTalkDTADb database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="0af83-104">Asegúrese de que servicio del Agente SQL está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0af83-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2.  <span data-ttu-id="0af83-105">Asegúrese de que el trabajo de archivo y purga esté en ejecución y que se esté realizando correctamente.</span><span class="sxs-lookup"><span data-stu-id="0af83-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3.  <span data-ttu-id="0af83-106">Compruebe que hay suficiente espacio disponible en disco para los archivos DTADb y para el crecimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0af83-106">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>