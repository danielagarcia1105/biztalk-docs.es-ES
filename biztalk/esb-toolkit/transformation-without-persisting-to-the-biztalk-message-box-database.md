---
title: "Transformación sin almacenar en la base de datos de cuadro de mensaje de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f5b4caf-88e9-41dd-a644-e229e411a4a7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407725509121948619e4eb05b583f6c8c1362f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a>Transformación sin almacenar en la base de datos de cuadro de mensaje de BizTalk
En este caso de uso, una llamada a un servicio Web realiza la transformación en tiempo real de un mensaje, basado en la resolución de tiempo de ejecución de la asignación correspondiente para aplicar y devuelve el resultado transformado. Figura 1 muestra una vista esquemática del proceso.  
  
 ![Transformación sin almacenar](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3-TransformationWithout")  
  
 **Figura 1**  
  
 **Transformación de un mensaje sin almacenar en la base de datos de cuadro de mensaje de Microsoft BizTalk Server**  
  
 El ejemplo de servicios de transformación que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Si la usa, puede llamar al servicio de transformación de ESB; Esto le permite probar las transformaciones y asignaciones, tal y como se va a programar componentes y las directivas en el motor de reglas de negocio de BizTalk Server.  
  
 Para obtener más información, consulte [instalar y ejecutar el ejemplo de servicio de transformación](../esb-toolkit/installing-and-running-the-transformation-service-sample.md).  
  
> [!NOTE]
>  No confunda el servicio de transformación que se hace referencia aquí con las operaciones de transformación dinámica realizadas por el agente de transformación de BizTalk Server. El servicio de transformación es un servicio Web de alto rendimiento que reduce significativamente la latencia llamando directamente al servidor BizTalk Server sin tener que pasar a través de la base de datos de cuadro de mensaje.