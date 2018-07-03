---
title: Los procesos privados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, trading partners
- private processes, about private processes
- private processes, orchestrations
- private processes
- orchestrations, private-process orchestrations
- trading partners, private processes
- BTARN, private processes
- business processes, private processes
ms.assetid: 0c5895eb-22c1-431f-a769-ae6ca05d1e45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff99f03b3a38ff9d8c1c33ec16b108e5bd58ca7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967493"
---
# <a name="private-processes"></a>Procesos privados
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implementa procesos empresariales internos de una organización como procesos privados. Los procesos públicos controlan procesos empresariales que implican la integración con socios comerciales. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] aísla el contenido del servicio de procesamiento y la integración de back-end (en proceso privado) de RosettaNet Implementation Framework (RNIF) de control (en el proceso público).  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa procesos privados como orquestaciones de BizTalk de larga ejecución. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] utiliza una orquestación de procesos de privados en el lado del iniciador y otra en el lado de servicio de respuesta. Cada proceso privado interpreta y procesa la parte del mensaje de contenido del servicio, entrante o saliente. Proceso privado envía el contenido del servicio, o lo recibe desde el proceso público. Un proceso privado no controla los encabezados y no lleva a cabo el procesamiento de RNIF. Lo deja el proceso público.  
  
 En un escenario empresarial, normalmente podría haber un proceso privado para cada esquema de mensaje PIP. Sin embargo, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye dos orquestaciones de proceso privado que pueden procesar cualquier mensaje PIP. Una orquestación es para el proceso de iniciador (PrivateInitiator.odx, consulte [ejemplo de PrivateInitiator &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) y otra para el proceso de servicio de respuesta (PrivateResponder.odx, consulte [PrivateResponder Ejemplo &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)). Tendrá que personalizar los procesos privados que se va a adaptar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] a sus procesos empresariales específicos.  
  
 El SDK también incluye un proceso que implementa un proceso de Respondedor privado PIP específico que incorpore una regla de negocios (PIP3A4PrivateResponder.odx, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)).  
  
 Proceso privado cambia el formato del contenido del servicio desde el formato de back-end línea de negocio (LOB) a XML. Tan pronto como se encuentra en formato XML, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesa el contenido del servicio, y el proceso público agrega encabezados compatibles con RNIF para el contenido del servicio para la transmisión.  
  
 Proceso privado se conecta a las aplicaciones de línea de negocio de back-end a través de las tablas MessageToLOB y MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. Esta base de datos administra la comunicación entre [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] y las aplicaciones de LOB. La aplicación LOB usa una interfaz para tener acceso a las tablas de base de datos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Proceso privado del iniciador](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [Proceso privado del respondedor](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)