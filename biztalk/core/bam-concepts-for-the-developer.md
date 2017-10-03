---
title: Conceptos BAM para que el programador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c26d0aed-821c-4e1f-9cc9-9375a2ba28de
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e407121e9f71707b45f95e77a8520ed30df3b33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-concepts-for-the-developer"></a>Conceptos de BAM para el programador
Como programador de BAM, es necesario familiarizarse con los conceptos BAM importantes, por ejemplo, las actividades, continuaciones y referencias. Además, debe comprender las diferencias entre el procesamiento de seguimiento y el procesamiento transaccional.  
  
## <a name="what-is-a-bam-activity"></a>¿Qué es una actividad de BAM?  
 Una actividad de BAM es la definición de qué datos son interesantes para obtener un elemento en el proceso empresarial (por ejemplo, un pedido de compra único). Define qué columnas están en la base de datos de BAM.  
  
 Una instancia de una actividad representa una unidad de trabajo en el negocio, como un pedido o una aplicación de préstamo. Una actividad especifica una lista de hitos (el historial de la actividad) y de datos de interés. La instancia de una actividad se manifiesta como fila única en la base de datos de importación principal de BAM. Solo existe un único valor para los elementos de datos de dicha instancia de la actividad.  
  
 Una actividad se usa para mostrar los hitos y datos acerca de esta unidad de trabajo al usuario empresarial final o trabajador de información. Por ejemplo, la actividad definida en el ejemplo SDK de BAM contiene hitos, como “Pagado” y "Enviar", así como datos de interés, por ejemplo “Cantidad total”.  
  
 Las actividades de BAM a menudo se asignan directamente a un proceso empresarial, aunque como una abstracción de alto nivel, una actividad es independiente de la implementación actual de la infraestructura de TI.  
  
 Su trabajo como programador consiste en mantener esta abstracción exponiendo los hitos relevantes y los datos de la implementación en el contexto de una actividad específica.  
  
## <a name="what-is-a-continuation"></a>¿Qué es una continuación?  
 Las continuaciones proporcionan a la infraestructura de BAM la siguiente información:  
  
-   El orden en que se espera que se produzcan los eventos  
  
-   Un medio para controlar cualquier cambio en el Id. único con el que se correlacionan los elementos de evento  
  
 Para obtener más información acerca de las continuaciones y cómo se utilizan, consulte [nodos Continuation y ContinuationID](../core/continuation-and-continuationid-nodes.md).  
  
## <a name="what-is-a-reference"></a>¿Qué es una referencia?  
 Una referencia (también conocida como actividad relacionada) especifica una relación entre una actividad y algún otro elemento. Los ejemplos de elementos que se pueden relacionar son otra actividad o una ubicación de documentación.  
  
> [!NOTE]
>  Al especificar una actividad como actividad relacionada, a diferencia de lo que ocurre con una actividad de continuación, no se impide que la actividad actual se complete si la actividad relacionada no se ha completado.  
  
## <a name="tracking-and-transactional-processing"></a>Procesamiento transaccional y de seguimiento  
 La escritura de código de BAM proporciona el control del modo en que se realiza el seguimiento de los datos, es decir, mediante el procesamiento transaccional o de seguimiento. De forma predeterminada, BAM asigna la misma importancia al seguimiento y al procesamiento. Esto significa que si se produce un error en la función de seguimiento o en el proceso de transacción, no se permite continuar con ninguno de ellos. No se graba nada en la base de datos de seguimiento y la transacción se revierte. Puede que no sea el método preferido para realizar el seguimiento de la solución. Mediante el desarrollo de BAM, puede determinar si tiene preferencia el procesamiento transaccional o de seguimiento.  
  
 En la tabla siguiente se describen los modos de seguimiento de datos en BAM.  
  
|Escenario|Descripciones|  
|--------------|------------------|  
|Preferencia de seguimiento sobre procesamiento|Si el proceso se realiza correctamente, escriba la información de seguimiento.<br /><br /> Si se produce un error en el proceso, escriba la información acerca del error.|  
|Procesamiento igual a seguimiento|Si se produce un error en el seguimiento o en el procesamiento, reviértalo todo.|  
|Preferencia de procesamiento sobre seguimiento|Si el proceso se realiza correctamente y se produce un error en la función de seguimiento, continúe con el procesamiento.|