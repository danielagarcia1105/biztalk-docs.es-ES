---
title: "El valor no puede ser vacío ni ser nulo para operadores distintos de existe | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44de42c8-eab7-4b13-b55a-d33eabe75c52
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5e257b78df8bf872764542d711637d33714349
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-value-cannot-be-empty-or-null-for-an-operator-other-than-exists"></a>El valor no puede estar vacío ni nulo para operadores distintos de Existe.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|ValueCannotBeNullOrEmpty|  
|Texto del mensaje|El valor no puede estar vacío ni nulo para operadores distintos de Existe.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido debido a que el operador no era Existe, pero el valor especificado estaba vacío o era nulo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI. Asegúrese de que, si el operador para una fila no es Existe, el valor especificado no está vacío ni es nulo.