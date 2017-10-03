---
title: '&#39; X &#39; y &#39; Y &#39; Opcionalidad | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- segments, Y optionality
- segments, SegmentDataElements table
- SegmentDataElements table
- segments, X optionality
ms.assetid: 8a59b407-95a2-45ba-a8d6-db4154c91d7b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320e0188a0987601daf65c011cc24aabc49b14cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="39x39-and-39y39-optionality"></a>&#39; X &#39; y &#39; Y &#39; Definir la opcionalidad como
La tabla SegmentDataElements en la base de datos de Access de HL7 contiene varios elementos de datos (campos) que se han establecido como **Req/Opt = X**, lo que significa que el estándar HL7 no asociar este campo a este evento de desencadenador, como se muestra en el tabla siguiente.  
  
|Segment|Versión|Capítulo|Elemento de datos|Necesario /<br /><br /> Opcional|Informe|Number|HTML estándar|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|OBX|2.4|7.4.2.9|00577|X|S|5|ch07.htm #Heading113|  
|OBX|2.4|7.4.2.8|00576|X||0|ch07.htm #Heading112|  
|OBX|2.4|7.4.2.6|00574|X||0|ch07.htm #Heading107|  
|OBX|2.4|7.4.2.17|00936|X|S|0|ch07.htm #Heading121|  
  
 Puesto que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] no especifica los eventos de desencadenador, decidir qué las reglas necesarios u opcionales, o debe ser opcionalidad. Según las condiciones del sitio local, se puede aplicar reglas de opcionalidad. De forma predeterminada, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporciona los 23 campos aparece como "X" como campos opcionales.  
  
> [!NOTE]
>  Valor "Y" es un error en la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] base de datos de Access. [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]se supone que todos los valores de **Y** y **en blanco** son opcionales.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)