---
title: Ejecutar el ejemplo de resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c933839f-13e6-4b49-9838-2773e3f99b64
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a61262bab3c3abeb7a4eb7113f09d8d3f7e8db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983133"
---
# <a name="running-the-dynamic-resolution-sample"></a><span data-ttu-id="a38c7-102">Ejecutar el ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="a38c7-102">Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="a38c7-103">Para ejecutar uno de los ejemplos de casos de uso, importa el archivo de enlace de Microsoft BizTalk adecuado en la aplicación de GlobalBank.ESB BizTalk y, a continuación, colocar un mensaje adecuado en la carpeta de entrada de ejemplo o llamar al servicio Web de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a38c7-103">To execute one of the use case examples, you import the appropriate Microsoft BizTalk binding file into the GlobalBank.ESB BizTalk application and then either drop a suitable message into the sample input folder or call the sample Web service.</span></span> <span data-ttu-id="a38c7-104">El ejemplo de resolución dinámica admite dos escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="a38c7-104">The Dynamic Resolution sample supports two main scenarios:</span></span>  
  
- <span data-ttu-id="a38c7-105">[Escenarios de mensajería unidireccional para el ejemplo de resolución dinámica](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a38c7-105">[One-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="a38c7-106">La resolución dinámica ejemplo es compatible con este escenario con una carpeta de entrega de archivos como la publicación punto a Microsoft BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a38c7-106">The Dynamic Resolution sample supports this scenario using a file drop folder as the publication point into Microsoft BizTalk.</span></span>  
  
- <span data-ttu-id="a38c7-107">[Escenarios de mensajería bidireccionales para el ejemplo de resolución dinámica](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a38c7-107">[Two-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="a38c7-108">El ejemplo de resolución dinámica es compatible con este escenario mediante el servicio ubicado en la NorthAmerican Web http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx como la publicación de puntos en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a38c7-108">The Dynamic Resolution sample supports this scenario using the NorthAmerican Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx as the publication point into BizTalk.</span></span>  
  
  <span data-ttu-id="a38c7-109">Para comprender cómo el ejemplo usa el distribuidor de ESB y componentes de canalización de desensamblador de distribuidor de ESB, consulte [dinámica resolución ejemplo funcionamiento](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="a38c7-109">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>