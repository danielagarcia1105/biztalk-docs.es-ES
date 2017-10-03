---
title: "El elemento de lote excedía el recuento de caracteres máximo configurado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ad12733-295a-43ba-8147-34c8716c2d37
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dac259db250a88e434efb649a2baf2e75b805a40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-element-exceeded-the-maximum-configured-character-count"></a>El elemento por lotes ha excedido el recuento de caracteres máximo configurado.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|MessageExceededCharacterCount|  
|Texto del mensaje|El elemento por lotes ha excedido el recuento de caracteres máximo configurado.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la orquestación por lotes no pudo generar el intercambio por lotes porque el número de caracteres de un elemento de lote seleccionado por la orquestación de lote supera el número de caracteres especificado por la propiedad "Número máximo de caracteres de un intercambio" de los criterios de lanzamiento de lote. El elemento de lote que genera este mensaje de error no será el primero seleccionado para un lote, sino uno después del primer elemento que ya se haya procesado por lotes. Tenga en cuenta que el número de caracteres comparado con el máximo no incluye el número de caracteres del sobre.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
1.  Aumente la propiedad "Número máximo de caracteres de un intercambio" de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI para la entidad como receptor de intercambio. Para ello, debe detener la instancia de orquestación, aumentar el número máximo de caracteres en la propiedad y, a continuación, reiniciar la instancia de orquestación.  
  
2.  Pida al remitente que envíe conjuntos de transacciones con menos caracteres que el número máximo de caracteres.