---
title: Tutorial de bucle invertido | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b013eb65320dc36dd1319d7332e45ed54b2444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="loopback-tutorial"></a>Tutorial de bucle invertido
Este tutorial contiene los pasos detallados que describen cómo se puede usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para simular una implementación de procesos entre la organización principal y de los asociados en un único equipo.  
  
 En un entorno de producción real, la implementación de la organización de socios comerciales reside en un equipo remoto. Este tutorial usa la utilidad de bucle invertido para crear un espejo de acuerdo para simular al socio comercial en el mismo equipo comercial. El uso de un escenario de bucle invertido único equipo funciona con fines de desarrollo y prueba. Se recomienda que realice para que no utilice la utilidad de bucle invertido en un entorno de producción.  
  
 Este escenario de bucle invertido no es compatible con la firma de mensajes y, por tanto, no admite sin repudio.  
  
 Este escenario admite el cifrado de mensajes si tiene una entidad de certificación configurada y tiene una clave privada para el cifrado disponible para fines de prueba.  
  
 En este tutorial, crear una organización principal, una organización asociada, un acuerdo comercial, use la utilidad de bucle invertido para crear un acuerdo reflejado y, a continuación, ejecutar un proceso de ejemplo para comprobar el escenario de bucle invertido.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparar el Tutorial](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [Paso 1: Crear la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [Paso 2: Crear la organización del asociado](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [Paso 3: Modificar el proceso de la interfaz de socio comercial](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [Paso 4: Crear un acuerdo comercial](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [Paso 5: Crear un acuerdo de reflejo](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [Paso 6: Iniciar orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [Paso 7: Crear un mensaje de LOB de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [Paso 8: Ver los mensajes en las bases de datos BTARN](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)