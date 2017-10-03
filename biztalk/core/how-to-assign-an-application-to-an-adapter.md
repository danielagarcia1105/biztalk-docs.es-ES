---
title: "Cómo asignar una aplicación a un adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1ea2773-c53c-40a0-a312-015191746451
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5052d06576988ed71da8458a9d55115fb0b1c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-an-application-to-an-adapter"></a><span data-ttu-id="c1b75-102">Cómo asignar una aplicación a un adaptador</span><span class="sxs-lookup"><span data-stu-id="c1b75-102">How to Assign an Application to an Adapter</span></span>
<span data-ttu-id="c1b75-103">Para procesar información entre una aplicación local y un servidor remoto, el adaptador debe tener una o más aplicaciones asignadas.</span><span class="sxs-lookup"><span data-stu-id="c1b75-103">To process information between a local application and a remote server, an adapter must have one or more applications assigned to it.</span></span>  
  
### <a name="to-assign-an-application-to-an-adapter"></a><span data-ttu-id="c1b75-104">Para asignar una aplicación a un adaptador</span><span class="sxs-lookup"><span data-stu-id="c1b75-104">To assign an application to an adapter</span></span>  
  
1.  <span data-ttu-id="c1b75-105">Agregar la aplicación al adaptador mediante `ISSOPSAdmin.AssignApplicationToAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c1b75-105">Add the application to the adapter by using `ISSOPSAdmin.AssignApplicationToAdapter`.</span></span>  
  
2.  <span data-ttu-id="c1b75-106">Puede recuperar la lista actual de las aplicaciones asignadas a un adaptador mediante el uso de `ISSOAdmin.GetApplicationsForAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c1b75-106">You can retrieve the current list of applications assigned to an adapter by using `ISSOAdmin.GetApplicationsForAdapter`.</span></span>  
  
3.  <span data-ttu-id="c1b75-107">Una vez haya terminado, puede quitar una aplicación de un adaptador mediante `ISSOPSAdmin.RemoveApplicationFromAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c1b75-107">Once you are finished, you can remove an application from an adapter by using `ISSOPSAdmin.RemoveApplicationFromAdapter`.</span></span>