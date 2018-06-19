---
title: Ejecutar el ejemplo de resolución dinámica | Documentos de Microsoft
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
ms.openlocfilehash: e613934c44db03cf29edbf3fff4ef34d6b946577
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300052"
---
# <a name="running-the-dynamic-resolution-sample"></a><span data-ttu-id="ea48a-102">Ejecutar el ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="ea48a-102">Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="ea48a-103">Para ejecutar uno de los ejemplos de casos de uso, importa el archivo de enlace de Microsoft BizTalk correspondiente a la aplicación de GlobalBank.ESB BizTalk y, a continuación, coloca un mensaje adecuado en la carpeta de entrada de ejemplo o llame al servicio Web de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea48a-103">To execute one of the use case examples, you import the appropriate Microsoft BizTalk binding file into the GlobalBank.ESB BizTalk application and then either drop a suitable message into the sample input folder or call the sample Web service.</span></span> <span data-ttu-id="ea48a-104">El ejemplo de resolución dinámica admite dos escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="ea48a-104">The Dynamic Resolution sample supports two main scenarios:</span></span>  
  
-   <span data-ttu-id="ea48a-105">[Escenarios de mensajería unidireccionales para el ejemplo de resolución dinámica](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ea48a-105">[One-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="ea48a-106">La resolución dinámica ejemplo es compatible con este escenario mediante una carpeta de entrega de archivos como la publicación punto a Microsoft BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea48a-106">The Dynamic Resolution sample supports this scenario using a file drop folder as the publication point into Microsoft BizTalk.</span></span>  
  
-   <span data-ttu-id="ea48a-107">[Escenarios de mensajería bidireccionales para el ejemplo de resolución dinámica](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ea48a-107">[Two-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="ea48a-108">El ejemplo de resolución dinámica admite este escenario mediante el servicio NorthAmerican Web situado en http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx como la publicación punto a BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea48a-108">The Dynamic Resolution sample supports this scenario using the NorthAmerican Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx as the publication point into BizTalk.</span></span>  
  
 <span data-ttu-id="ea48a-109">Para comprender cómo el ejemplo usa el distribuidor de ESB y componentes de canalización de desensamblador de distribuidor de ESB, consulte [dinámica resolución ejemplo funcionamiento del](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="ea48a-109">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>