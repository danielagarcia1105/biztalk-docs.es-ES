---
title: Según el conjunto de delimitadores especificado no pudo generarse ningún valor de tiempo válido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e22958-e1fa-474d-85a2-aa69e05b7228
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00b8b06922109ae5817c67b26f1a23977d1b607b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230796"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-time-value-could-be-generated"></a>No pudo generarse ningún valor de Hora válido según el conjunto de delimitadores especificado
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|No pudo generarse ningún valor de Hora válido según el conjunto de delimitadores especificado. Utilice otro conjunto de delimitadores.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío EDI no pudo generar un valor de hora válido debido a que un carácter usado en un campo Hora del intercambio saliente era el mismo que un carácter separador.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este error, cambie los valores de separador que la canalización de envío EDI usa para crear un mensaje de modo que ningún carácter separador sea el mismo que un carácter usado en un campo de hora. Realice una de las siguientes operaciones:  
  
-   Para un intercambio X12 que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento ISA para la entidad como receptor del intercambio.  
  
-   Para un intercambio X12 que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento ISA.  
  
-   Para un intercambio EDIFACT que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento UNA para la entidad como receptor del intercambio.  
  
-   Para un intercambio EDIFACT que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento UNA.