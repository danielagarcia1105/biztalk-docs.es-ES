---
title: Fragmentado por lotes entrantes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0807bbe83ea2f477a7e1625488ebbecf578f3adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fragmented-inbound-batch"></a>Fragmentados por lotes entrantes
Puede configurar [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para recibir un lote de mensajes, extraer los mensajes del lote y, a continuación, enrutar los mensajes individuales en el sistema de destino. Si habilita la fragmentación, los fragmentos por lotes entrantes en mensajes individuales; en caso contrario, se procesa el lote y se enruta como un único 'batch' o el intercambio. Use el Explorador de configuración de BTAHL7 para habilitar el procesamiento por lotes. Para obtener más información acerca de cómo habilitar el procesamiento por lotes, vea [configurar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).  
  
 A continuación describen un escenario típico por lotes entrantes fragmentados:  
  
1.  Una aplicación de línea de negocio, que se ejecuta en el sistema A, envía un lote de mensajes a BTAHL7.  
  
     Mensajes por lotes pueden estar en dos formatos diferentes. BTAHL7 puede procesar los siguientes formatos:  
  
    -   Formato 1: Incluye un encabezado de archivo y par de finalizador (FHS/FTS) y uno o más encabezado de lote y finalizadores (BHS/BTS).  
  
        ```  
        FHS  
        BHS  
        MSH  
        .............  
        MSH  
        ...........  
        BTS  
        BHS  
        MSH  
        ..............  
        MSH  
        ...............  
        BTS  
        FTS  
        ```  
  
    -   Formato 2: No contiene contenedores de archivos y por lotes de HL7 definido y suspende una serie de mensajes en una secuencia.  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  BTAHL7 crea los mensajes individuales del lote y, a continuación, comprueba los mensajes individuales con los esquemas adecuados.  
  
3.  BTAHL7 envía un mensaje de confirmación independiente en el sistema A para cada mensaje extraído del lote.  
  
4.  BTAHL7 enruta los mensajes individuales en el sistema de destino en función de la información de enrutamiento en los mensajes individuales, en lugar de en el encabezado del mensaje por lotes.  
  
    > [!NOTE]
    >  BTAHL7 no valida los encabezados/finalizadores por lotes y el archivo cuando la **FHS3** campo (entidad de envío) contiene un socio comercial que tenga habilitada la fragmentación.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)