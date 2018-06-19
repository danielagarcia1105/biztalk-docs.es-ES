---
title: Conjunto de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70722adc1a099d340b862d38574b44391954aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241460"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a>Grupo de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|DelimiterOutOfRange|  
|Texto del mensaje|Grupo de delimitadores {0} no válido; al menos uno de los delimitadores está fuera del intervalo permitido de 0 a 127.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante, pues uno o varios separadores del intercambio estaban fuera del intervalo de valores del conjunto de caracteres ASCII.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que cada separador del intercambio se encuentra en el conjunto de caracteres ASCII y vuelva a enviar el mensaje.