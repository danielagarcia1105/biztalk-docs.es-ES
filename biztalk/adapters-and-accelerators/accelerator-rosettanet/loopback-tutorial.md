---
title: Tutorial de bucle invertido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97714d5f7e604acbb798739fc4eb545a07968980
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010101"
---
# <a name="loopback-tutorial"></a>Tutorial de bucle invertido
Este tutorial contiene los pasos detallados que describen cómo puede usar Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para simular una implementación de proceso entre la organización principal y socios en un único equipo.  
  
 En un entorno de producción real, la implementación de la organización del asociado que reside en un equipo remoto. Este tutorial usa la utilidad de bucle invertido para crear un espejo de acuerdo para simular al socio comercial en el mismo equipo comercial. Uso de un escenario de bucle invertido de equipo único funciona para fines de desarrollo y pruebas. Se recomienda que no desea para usar la utilidad de bucle invertido en un entorno de producción.  
  
 Este escenario de bucle invertido no es compatible con la firma de mensajes y, por tanto, no admite sin repudio.  
  
 Este escenario admite el cifrado de mensajes si tiene configurada una entidad de certificación, y tiene una clave privada de cifrado disponible para fines de prueba.  
  
 En este tutorial, cree la organización principal, una organización asociada, un acuerdo comercial, use la utilidad de bucle invertido para crear un acuerdo reflejado y, a continuación, ejecute un proceso de ejemplo para comprobar el escenario de bucle invertido.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparación para el tutorial](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [Paso 1: Crear la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [Paso 2: Crear la organización asociada](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [Paso 3: Modificar el proceso de interfaz de socio (PIP)](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [Paso 4: Crear un acuerdo comercial](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [Paso 5: Crear un acuerdo reflejado](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [Paso 6: Iniciar las orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [Paso 7: Crear un mensaje de LOB de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [Paso 8: Ver los mensajes en las bases de datos de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)