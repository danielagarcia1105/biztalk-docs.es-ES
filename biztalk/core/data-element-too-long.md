---
title: Elemento de datos demasiado largo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf608cc1-d482-4e19-8f56-10d9e03feb79
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbfe63fccc442c35411bfae04c7f27629ce066ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-element-too-long"></a>Elemento de datos demasiado largo.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Elemento de datos demasiado largo.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción de EDI o la canalización de envío de EDI no pudo procesar el intercambio entrante porque un elemento de datos tenía una longitud mayor que la máxima que especifica el esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, disminuya de tamaño el elemento de datos del intercambio que era demasiado largo de modo que quede por debajo de la longitud máxima. Para determinar la longitud máxima, abra el esquema en la carpeta \XSD_Schema, busque en el identificador del elemento de datos e identifique cuál es el valor de maxLength.