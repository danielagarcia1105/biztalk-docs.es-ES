---
title: Control externamente enviado excepciones mediante un controlador personalizado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fa661e-d391-47c0-92d5-1d0c45b5963d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba3fc49756619f77188f0a311ff46eb18e7f0b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294060"
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a><span data-ttu-id="cf36e-102">Control externamente enviado excepciones mediante un controlador personalizado</span><span class="sxs-lookup"><span data-stu-id="cf36e-102">Handling Externally Submitted Exceptions Using a Custom Handler</span></span>
<span data-ttu-id="cf36e-103">En este caso de uso, un cliente externo envía un mensaje de excepción a través de un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="cf36e-103">In this use case, an external client submits an exception message through a Web service.</span></span> <span data-ttu-id="cf36e-104">Un puerto de envío configurado previamente con el componente de canalización de codificador de excepción de ESB, se suscribe al mensaje de error; procesa y lo almacena como un archivo de disco que se puede ver con Microsoft InfoPath, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="cf36e-104">A send port, preconfigured with the ESB Exception Encoder pipeline component, subscribes to the fault message; it processes and persists it as a disk file that you can view using Microsoft InfoPath, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="cf36e-105">![Tratamiento de excepciones externas](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")</span><span class="sxs-lookup"><span data-stu-id="cf36e-105">![Handling External Exceptions](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")</span></span>  
  
 <span data-ttu-id="cf36e-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="cf36e-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="cf36e-107">**Controlar los mensajes entrantes de excepción o error y almacenarla en un archivo de disco**</span><span class="sxs-lookup"><span data-stu-id="cf36e-107">**Handling incoming exception or fault messages and persisting to a disk file**</span></span>  
  
 <span data-ttu-id="cf36e-108">El ejemplo de servicio de control de excepciones incluido con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="cf36e-108">The Exception Handling Service Sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="cf36e-109">Muestra cómo utilizar el servicio de la excepción de ESB como un mecanismo universal para enviar mensajes de error de las aplicaciones externas que se almacenará en la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] base de datos de administración de excepciones.</span><span class="sxs-lookup"><span data-stu-id="cf36e-109">It shows how to use the ESB Exception Service as a universal mechanism to submit fault messages from external applications that will be stored in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] exception management database.</span></span> <span data-ttu-id="cf36e-110">Para obtener más información, consulte [ejecutar el ejemplo de servicio de control de excepciones](../esb-toolkit/running-the-exception-handling-service-sample.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-110">For more information, see [Running the Exception Handling Service Sample](../esb-toolkit/running-the-exception-handling-service-sample.md).</span></span>