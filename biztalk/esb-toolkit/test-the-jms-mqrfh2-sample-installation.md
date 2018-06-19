---
title: Probar la instalación de ejemplo JMS MQRFH2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 965e985d-f0fe-4b0f-b01b-cf98d1e2f6a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5970f12479cddfb6a635cbd00dd139495a2f6242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294620"
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a><span data-ttu-id="0b7ed-102">Probar la instalación de ejemplo de MQRFH2 JMS</span><span class="sxs-lookup"><span data-stu-id="0b7ed-102">Test the JMS MQRFH2 Sample Installation</span></span>
<span data-ttu-id="0b7ed-103">Puede comprobar si hay una instalación correcta y el funcionamiento de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] MQRFH2 de JMS ejemplo antes de ejecutar cualquiera de los escenarios de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-103">You can check for successful installation and operation of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 sample before you execute any of the sample scenarios.</span></span>  
  
 <span data-ttu-id="0b7ed-104">**Para probar la instalación de ejemplo MQRFH2 de JMS**</span><span class="sxs-lookup"><span data-stu-id="0b7ed-104">**To test the JMS MQRFH2 sample installation**</span></span>  
  
1.  <span data-ttu-id="0b7ed-105">Use "RFHUtil" utilidad para escribir los mensajes de prueba en la carpeta \Source\Samples\JMS\Test\Data\Load en la cola con el nombre de ESB de prueba de JMS. JMS. EJEMPLO. SENDTOBIZTALK.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-105">Use the "RFHUtil" JMS test utility to write the test messages in the \Source\Samples\JMS\Test\Data\Load folder to the queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
2.  <span data-ttu-id="0b7ed-106">El ejemplo envía el mensaje a la cola de destino y una copia del mensaje a la cola de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-106">The sample sends the message to the destination queue and a copy of the message to the reply queue.</span></span>