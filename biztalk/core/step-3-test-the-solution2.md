---
title: 'Paso 3: Probar el 2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0e484a9f6af788775ec4ae7309965327378267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-solution"></a>Paso 3: Probar la solución
![Paso 3 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará cómo la solución EAI procesa los mensajes.  
  
 **Propósito:** en este paso, comprobará que la orquestación EAIProcess procesa los mensajes correctamente. Para ello, soltará los mensajes de muestra en la ubicación de recepción especificada para la aplicación EAI. Si la solución EAI funciona correctamente, cuando la orquestación EAIProcess recibe un mensaje del almacén para solicitar más de 500 elementos, la orquestación genera un mensaje de solicitud de rechazo. Cuando la orquestación EAIProcess recibe un mensaje del almacén para solicitar menos de 500 elementos, la orquestación pasa el mensaje al sistema ERP.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso debe completar [paso 2: configurar e iniciar la aplicación](../core/step-2-configure-and-start-the-application1.md).  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-test-the-eai-solution"></a>Para probar la solución EAI  
  
1.  Abra el Explorador de Windows y vaya a **C:\BTSTutorials\WareHouse**.  Esta carpeta se crea al instalar los archivos del tutorial.  
  
2.  Copia **RequestInstance.XML** y péguelo en **C:\BTSTutorials\WareHouse\Request**.  
  
3.  Cuando el archivo desaparezca, compruebe **C:\BTSTutorials\ERP\Request**.  
  
4.  En el Explorador de Windows, vaya a **C:\BTSTutorials\WareHouse**.  
  
5.  Copia **RequestInstance (por encima del límite). XML** y péguelo en **C:\BTSTutorials\WareHouse\Request**.  
  
6.  Cuando el archivo desaparezca, compruebe **C:\BTSTutorials\WareHouse\RequestDecline**.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Ha probado la solución EAI mediante la colocación de mensajes de muestra en la ubicación de recepción de la aplicación EAI.  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Implementar los proyectos](../core/step-1-deploy-the-projects.md)   
 [Paso 2: Configurar e iniciar la aplicación](../core/step-2-configure-and-start-the-application1.md)