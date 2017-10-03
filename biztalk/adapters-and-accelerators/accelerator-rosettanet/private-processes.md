---
title: Procesos privados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b28bf49af1305220d96f129080b274b5391495eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="private-processes"></a>Procesos privados
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implementa procesos empresariales internos de una organización como procesos privados. Procesos públicos controlen procesos empresariales que implican la integración con socios comerciales. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]aísla el procesamiento de contenido del servicio y la integración de back-end (en el proceso privado) de RosettaNet Implementation Framework (RNIF) (en el proceso público).  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]implementa procesos privados como orquestaciones de BizTalk de larga duración. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]utiliza una orquestación de procesos privados en el lado del iniciador y otra en el lado de servicio de respuesta. Cada proceso privado interpreta y procesa la parte del mensaje de contenido del servicio, entrante o saliente. El proceso privado envía el contenido del servicio a o recibe desde el proceso público. Un proceso privado no procesa encabezados y no lleva a cabo el procesamiento de RNIF. Deja el proceso público.  
  
 En un escenario empresarial, habrá normalmente un proceso privado para cada esquema de mensaje PIP. Sin embargo, la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye dos orquestaciones de proceso privado que pueden procesar cualquier mensaje PIP. Una orquestación es para el proceso de iniciador (PrivateInitiator.odx, consulte [PrivateInitiator ejemplo &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) y otra para el proceso de servicio de respuesta (PrivateResponder.odx, consulte [PrivateResponder ejemplo &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)). Tendrá que personalizar los procesos privados que se va a adaptar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] a sus procesos empresariales específicos.  
  
 El SDK también incluye un proceso que implementa un proceso de Respondedor privada específica de PIP incorpora una regla de negocios (PIP3A4PrivateResponder.odx, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)).  
  
 El proceso privado cambia el formato del contenido del servicio desde el formato de back-end línea de negocio (LOB) a XML. Tan pronto como se encuentra en formato XML, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesa el contenido del servicio, y el proceso público agrega encabezados compatible con RNIF para el contenido del servicio para su transmisión.  
  
 El proceso privado se conecta a las aplicaciones de línea de negocio de back-end a través de las tablas MessageToLOB y MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos. Esta base de datos controla la comunicación entre [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] y las aplicaciones LOB. La aplicación de LOB utiliza una interfaz para tener acceso a las tablas de base de datos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Proceso de iniciador privada](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [Proceso de respuesta privado](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)