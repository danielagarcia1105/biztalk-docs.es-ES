---
title: "El nombre de propiedad no es una cadena válida | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a0641e4-1267-44a0-8777-bd6e2baf1088
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 787d38dce9336eefa3715b5edd09db2cc426332b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-property-name-is-not-a-valid-string"></a>El nombre de propiedad no es una cadena válida.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|InvalidPropertyName|  
|Texto del mensaje|El nombre de propiedad no es una cadena válida.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que un nombre especificado para una propiedad en el cuadro de diálogo Filtro por lotes no era válido porque el nombre de la propiedad no era una cadena, como se requería.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI. Asegúrese de que todos los nombres de propiedades son cadenas.