---
title: "Infringido de condición de exclusión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e508da6-7edc-45c0-a7ab-f23337dc1b54
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5a508c113daf628491837adee119649ac17b478
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exclusion-condition-violated"></a>Infracción de condición de exclusión
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12DeExclusionConditionViolatedDescription|  
|Texto del mensaje|Infracción de condición de exclusión. Vea el valor del campo de la instancia para obtener detalles.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que no se pudo validar un intercambio X12 en tiempo de diseño (mediante la herramienta de validación XML) o bien en tiempo de ejecución, bien en la recepción o bien en el envío, debido a que un segmento de la instancia no superó una regla de exclusión de la validación de campos cruzados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de modificar el segmento que tuvo un error en la regla de exclusión de modo que supere la validación de campo cruzado y, a continuación, vuelva a ejecutar el proceso de validación.