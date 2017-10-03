---
title: "Probar la instalación de ejemplo JMS MQRFH2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 965e985d-f0fe-4b0f-b01b-cf98d1e2f6a4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5970f12479cddfb6a635cbd00dd139495a2f6242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a>Probar la instalación de ejemplo de MQRFH2 JMS
Puede comprobar si hay una instalación correcta y el funcionamiento de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] MQRFH2 de JMS ejemplo antes de ejecutar cualquiera de los escenarios de ejemplo.  
  
 **Para probar la instalación de ejemplo MQRFH2 de JMS**  
  
1.  Use "RFHUtil" utilidad para escribir los mensajes de prueba en la carpeta \Source\Samples\JMS\Test\Data\Load en la cola con el nombre de ESB de prueba de JMS. JMS. EJEMPLO. SENDTOBIZTALK.  
  
2.  El ejemplo envía el mensaje a la cola de destino y una copia del mensaje a la cola de respuesta.