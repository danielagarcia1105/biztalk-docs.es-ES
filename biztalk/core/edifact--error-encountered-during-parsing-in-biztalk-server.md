---
title: Error al analizar. El intercambio de Edifact que no contenía un grupo presentaba los errores siguientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550e5ca207bef7fdcb42ffcbd52e114ad3dc95ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239588"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a>Error al analizar. El intercambio Edifact que no contenía un grupo presentaba los errores siguientes
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EfactFunctionalGroupReceiveErrorWithoutGroup|  
|Texto del mensaje|Error al analizar. El intercambio de Edifact que no contenía un grupo, con el Id. de intercambio '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes:|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio EDIFACT entrante sin grupo debido a los errores indicados. Tenga en cuenta que en los intercambios EDIFACT los grupos son opcionales.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error y, a continuación, determine la resolución del problema en la ayuda del producto.