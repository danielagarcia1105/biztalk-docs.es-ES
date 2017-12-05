---
title: 'Paso 7: Crear un mensaje de LOB de ejemplo | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1246f56615381d2627db3058dc821ba85bf8b74d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-create-a-sample-lob-message"></a>Paso 7: Crear un mensaje de LOB de ejemplo
En este paso, se utiliza la utilidad de la aplicación de LOB para crear un mensaje de la línea de negocio (LOB) de ejemplo.  
  
### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a>Para crear un mensaje de ejemplo mediante la utilidad de la aplicación de LOB  
  
1.  En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK carpeta y, a continuación, haga doble clic en  **LOBApplication.exe**.  
  
2.  En el **aplicación LOB** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Nombre del perfil de inicio**|Tipo de **inicio**.|  
    |**Nombre del socio comercial**|Tipo de **asociado**.|  
    |**Nombre del PIP**|Tipo de **0c1**.|  
    |**Versión PIP**|Escriba **R01.02**.|  
    |**Nombre de archivo**|Haga clic en el botón de puntos suspensivos (**...** ) y mover a \< *unidad*:\>\Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances. Seleccione **0C1_Request.xml** en la lista de archivos y, a continuación, haga clic en **abiertos**.|  
    |**Categoría de mensaje**|Seleccione **acción** en la lista desplegable.|  
  
3.  En el **aplicación LOB** cuadro de diálogo, haga clic en **enviar mensaje**.  
  
 La aplicación de LOB genera un mensaje de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulando un mensaje original generado por una aplicación de LOB. Puede ver el estado del mensaje en la ventana de estado.  
  
> [!NOTE]
>  Los mensajes de ejemplo se supone que los identificadores de empresarial Global (GBI) para "Hogar" y "Asociado" son 123456789 y 987654321, respectivamente. Para usar un GBI diferente, debe modificar el contenido de estos archivos.  
  
## <a name="see-also"></a>Vea también  
 [Paso 8: Ver los mensajes en las bases de datos de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)