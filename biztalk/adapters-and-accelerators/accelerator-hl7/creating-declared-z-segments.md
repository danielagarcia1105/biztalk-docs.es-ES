---
title: Crear segmentos de Z declarado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae9148547f527d29238b6080cd499be8da7b7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-declared-z-segments"></a>Crear segmentos de Z declarado
Puede crear segmentos de Z declarados en cualquier nivel de un esquema (a diferencia de los segmentos no declarados de Z, que debe ser la última parte de un mensaje de varias parte, después de la parte del cuerpo).  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a>Para crear un segmento de Z en el Editor de BizTalk  
  
1.  En el Explorador de soluciones de Visual Studio, haga clic en el esquema al que desea agregar un segmento de Z y, a continuación, haga clic en **abiertos**.  
  
2.  En el Editor de BizTalk, haga clic en el nodo con el nombre del esquema, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.  
  
3.  Nombre del registro a partir del nombre de tres dígitos alfanuméricos, en mayúsculas, con el primer dígito que se va a "Z". (La etiqueta de segmento Z debe incluir tres caracteres). Insertar un carácter de subrayado (_) y, a continuación, agregue una descripción breve del segmento. La descripción debe contener uno o una serie de palabras, sin espacios en blanco, con la primera letra de cada palabra en mayúsculas. La última palabra debe ser "Segmento". (Un ejemplo es "ZPP_PatientPreferencesSegment.) Presione **ENTRAR**.  
  
4.  En el panel Propiedades, escriba las propiedades que desee para el segmento de Z, incluidos los **Data Structure Type** (nombre de esquema o xsd: anyType), **Max Occurs**, y **Min Occurs**.  
  
    > [!NOTE]
    >  Si especifica un tipo de estructura de datos para el registro, no podrá agregar un elemento de campo secundario.  
  
5.  En el Editor de BizTalk, haga clic en el nombre del segmento de Z, seleccione **Insertar nodo de esquema**, a continuación, haga clic en **elemento de campo secundario**.  
  
6.  Escriba el nombre del campo, empezando el nombre con los tres primeros dígitos del nombre del segmento, seguido por un punto y el número del campo, seguido por un carácter de subrayado y, a continuación, una breve descripción del campo. La descripción debe contener uno o una serie de palabras, sin espacios en blanco, con la primera letra de cada palabra en mayúsculas. Presione **ENTRAR**.  
  
7.  En el panel Propiedades, escriba las propiedades que desee para el segmento de Z, incluidos los **tipo de datos**, **Nillable**, **Fixed**, **Max Occurs**, y **Min Occurs**.  
  
8.  Para crear un campo con los componentes, cree el campo como un registro y, a continuación, cree un elemento secundario de ese registro para cada componente. Para crear un campo con subcomponentes, crear componentes como registros y el campo y los subcomponentes como elemento secundario elementos. Tenga en cuenta que los subcomponentes no pueden ser tipos de datos compuestos. Por ejemplo, para el segmento denominado ZPP_PatientPreferencesSegment, podría crear un campo de ZPP.1_Dietary y un componente de alergias PD.1 con un subcomponente de PD.1.1_FoodGroupAllergy. El subcomponente PD.1.1_FoodGroupAllergy tendría que ser un tipo de datos simple.  
  
## <a name="see-also"></a>Vea también  
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [Crear tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [Control de segmentos de Z no declarado](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)