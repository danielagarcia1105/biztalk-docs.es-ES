---
title: "Versión de grupo funcional no compatible | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715e6585-a07a-4060-a15b-0c9603fbef19
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b92b7844c750d9a709ac2376bb8f126a32119f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="functional-group-version-not-supported"></a>Versión de grupo funcional no compatible.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12FaGroupVersionNotSupportedDescription|  
|Texto del mensaje|Versión de grupo funcional no compatible.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque BizTalk Server no admite el número de versión en el segmento GS08 de un grupo funcional.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los números de versión de cada instancia del segmento GS08 en todos los grupos funcionales del intercambio son compatibles con BizTalk Server y vuelva a enviar el intercambio. Tenga en cuenta que las versiones estándar que admite BizTalk Server aparecen en el tema "Compatibilidad con el esquema de documento EDI" de la Ayuda del producto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].