---
title: 'Paso 7: Crear un mensaje de LOB de ejemplo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b8450f196a1619b55b08a0771508daafa421a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978005"
---
# <a name="step-7-create-a-sample-lob-message"></a>Paso 7: Crear un mensaje de LOB de ejemplo
En este paso, usará la utilidad de la aplicación de LOB para crear un mensaje de la línea de negocio (LOB) de ejemplo.  

### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a>Para crear un mensaje de ejemplo mediante la utilidad de la aplicación de LOB  

1. En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, desplácese a \< *unidad*\>: \Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK carpeta y, a continuación, haga doble clic en **LOBApplication.exe**.  

2. En el **aplicación LOB** diálogo cuadro, realice lo siguiente:  


   |       **Úselo**       |                                                                                                                       **Para ello**                                                                                                                       |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **Nombre del perfil principal**   |                                                                                                                       Tipo **inicio**.                                                                                                                       |
   | **Nombre del socio comercial** |                                                                                                                     Tipo **asociado**.                                                                                                                      |
   |       **Nombre PIP**       |                                                                                                                       Tipo **0c1**.                                                                                                                        |
   |     **Versión PIP**      |                                                                                                                      Escriba **R01.02**.                                                                                                                      |
   |      **Nombre de archivo**       | Haga clic en el botón de puntos suspensivos (**...** ) y mover a \< *unidad*:\>\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances . Seleccione **0C1_Request.xml** en la lista de archivos y, a continuación, haga clic en **abierto**. |
   |   **Categoría de mensaje**   |                                                                                                         Seleccione **acción** en la lista desplegable.                                                                                                         |


3. En el **aplicación LOB** cuadro de diálogo, haga clic en **enviar mensaje**.  

   La aplicación de LOB, genera un mensaje de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulando un mensaje original generado por una aplicación de LOB. Puede ver el estado del mensaje en la ventana de estado.  

> [!NOTE]
>  Los mensajes de ejemplo se suponen que los identificadores de negocio Global (GBI) para "Hogar" y "PARTNER" son 123456789 y 987654321, respectivamente. Para usar un GBI diferente, debe modificar el contenido de estos archivos.  

## <a name="see-also"></a>Vea también  
 [Paso 8: Ver los mensajes en las bases de datos de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
