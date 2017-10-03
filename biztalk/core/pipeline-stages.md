---
title: "Etapas de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- CATID_AssemblingSerializer component category
- CATID_Encoder component category
- pipelines, stages
- CATID_DisassemblingParser component category
- CATID_Validate component category
- ComponentCategory class attribute
- CATID_Decoder component category
- CATID_Any component category
- CATID_PartyResolver component category
- Execution Mode property
ms.assetid: ac50c48c-6ed5-4322-95cc-af55df6bcd1c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeb675f39cb39ade4230e6e39f798e95115aaf78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pipeline-stages"></a>Fases de la canalización
Este tema se describe la **modo de ejecución** afinidad de propiedad y fase.  
  
## <a name="execution-mode-property"></a>Propiedad Modo de ejecución  
 Durante la ejecución de una canalización, las fases de canalización pueden ejecutar solo el primer componente que reconozca el formato de mensaje o bien todos los componentes. La propiedad que determina el patrón de ejecución es **modo de ejecución**.  
  
> [!NOTE]
>  Esta propiedad es de solo lectura en las fases incluidas en las plantillas de canalización, pero la comprensión de su funcionamiento resulta importante.  
  
 Cuando el **modo de ejecución** propiedad está establecida en **todos los**, todos los componentes de la fase se ejecutan en el orden configurado. Este modo ejecuta varios componentes para completar una tarea lógica. En este caso, se producirá un error en tiempo de ejecución si alguno de los componentes se topa con un error al procesar un mensaje durante esta fase de canalización.  
  
 Cuando se utiliza una canalización para recibir mensajes en varios formatos, la **modo de ejecución** propiedad está establecida en **FirstMatch**. En este modo, solo se ejecuta el primer componente que reconozca el mensaje. Si ningún componente de la fase reconoce el mensaje, se producirá un error en tiempo de ejecución.  
  
 Tenga en cuenta que cada fase puede tener su propio **modo de ejecución** fases de configuración, por lo que diferentes dentro de una canalización pueden tener diferentes modos de ejecución.  
  
> [!NOTE]
>  En esta versión de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], todas las fases de un envío de canalización y todas las fases excepto desensamblar de una canalización de recepción tienen el valor de la **modo de ejecución** propiedad establecida en **todos los**. El valor de la **modo de ejecución** propiedad en la fase de desensamblado está establecida en **FirstMatch**. No se puede cambiar la **modo de ejecución** propiedad de una fase.  
  
#### <a name="to-read-pipeline-stage-properties"></a>Para leer las propiedades de fase de canalización  
  
1.  En el Diseñador de canalizaciones, haga clic en una forma de canalización.  
  
2.  En la ventana Propiedades, en la **General** sección, verá las siguientes propiedades:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Indica el nombre de la fase.|  
    |**Modo de ejecución**|Indica el patrón de ejecución de la fase.<br /><br /> Los valores válidos: **todos los** o **FirstMatch**|  
    |**Número mínimo de componentes**|Indica el número mínimo de componentes de canalización que pueden agregarse a la fase.|  
    |**Número máximo de componentes**|Indica el número máximo de componentes de canalización que pueden agregarse a la fase.|  
    |**StageID**|Indica el identificador único para la fase.|  
  
## <a name="stage-affinity"></a>Afinidad de fases  
 Los componentes de canalización tienen afinidad de fases, lo que significa que se crean para utilizarse en una o varias fases particulares de una canalización.  
  
 Componentes de canalización basados en COM express su afinidad de fases registrándose a sí mismos con el Id. de fase como categoría de implementación, mientras que. Componentes de canalización basados en red especifican su afinidad de fases mediante el uso de la **ComponentCategory** class (atributo). Tenga en cuenta que es posible que un componente para asociarse a más de una fase: componentes pueden tener más de una categoría de implementación o **ComponentCategory** atributo.  
  
 En la siguiente tabla se muestran las categorías de componentes disponibles y las fases asociadas.  
  
|Categoría de componentes|Fase en la que puede situarse el componente|Description|  
|------------------------|-----------------------------------------|-----------------|  
|CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}|Descodificar|Todos los componentes de descodificación deberían implementar esta categoría.|  
|CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}|Desensamblar|Todos los componentes de desensamblado y análisis deberían implementar esta categoría.|  
|CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}|Validar|Los componentes de validación deberían implementar esta categoría.|  
|CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}|resolverEntidad|Fase utilizada para el componente de resolución de entidades.|  
|CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}|Codificar|Todos los componentes de codificación deberían implementar esta categoría.|  
|CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}|Serializar|Todos los componentes de serialización y ensamblado deberían implementar esta categoría.|  
|CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}|Cualquiera de estas fases|Si un componente de canalización implementa esta categoría, significa que el componente puede situarse en cualquier fase de una canalización.|  
  
## <a name="see-also"></a>Vea también  
 [Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md)   
 [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)