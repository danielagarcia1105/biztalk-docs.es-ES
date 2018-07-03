---
title: '&#39;X&#39; y &#39;Y&#39; opcionalidad | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, Y optionality
- segments, SegmentDataElements table
- SegmentDataElements table
- segments, X optionality
ms.assetid: 8a59b407-95a2-45ba-a8d6-db4154c91d7b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed5b87216bd2d8e127ff032e3773b3f740835c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981525"
---
# <a name="39x39-and-39y39-optionality"></a>&#39;X&#39; y &#39;Y&#39; opcionalidad
La tabla SegmentDataElements en la base de datos de Access de HL7 contiene varios elementos de datos (campos) que se han establecido como **Req/Opt = X**, lo que significa que el estándar HL7 no asocia este campo con este evento de desencadenador, como se muestra en el tabla siguiente.  
  
|Segment|Versión|Capítulo|Elemento de datos|Necesario /<br /><br /> Opcional|Informe|Number|HTML estándar|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|OBX|2.4|7.4.2.9|00577|X|S|5|ch07.htm #Heading113|  
|OBX|2.4|7.4.2.8|00576|X||0|ch07.htm #Heading112|  
|OBX|2.4|7.4.2.6|00574|X||0|ch07.htm #Heading107|  
|OBX|2.4|7.4.2.17|00936|X|S|0|ch07.htm #Heading121|  
  
 Desde Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] no especifica los eventos de desencadenador, decidir qué las reglas obligatorias y opcionales, o debería estar opcionalidad. Según las condiciones del sitio local, puede decidir exigir reglas de opcionalidad. De forma predeterminada, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporciona el 23 campos aparece como "X", como los campos opcionales.  
  
> [!NOTE]
>  Valor "Y" es un error en la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] base de datos Access. [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] se supone que todos los valores de **Y** y **en blanco** son opcionales.  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)