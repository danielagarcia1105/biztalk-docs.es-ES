---
title: No según el conjunto de delimitadores especificado, se encontró ningún dígito válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08887f7d-8256-4de3-8db9-b890451521ff
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc117a9c9d08d664f397557ab08f9c6f2e7dc7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989229"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-digit-could-be-found"></a>No se encontró ningún dígito válido según el conjunto de delimitadores especificado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| Versión del producto |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    Identificador del evento     |                                                   -                                                    |
|  Origen del evento   |         EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
|    Componente    |                                               Motor EDI                                               |
|  Nombre simbólico  |                                                   -                                                    |
|  Texto del mensaje   | No se encontró ningún dígito válido según el conjunto de delimitadores especificado. Utilice otro conjunto de delimitadores. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI no encontró un dígito válido al generar un intercambio saliente porque un dígito usado en un campo del intercambio saliente era el mismo que un carácter separador.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar este error, cambie los valores de separador que la canalización de envío EDI usa para crear un mensaje de modo que ningún carácter separador sea el mismo que un dígito usado en un campo del intercambio saliente. Realice una de las siguientes operaciones:  
  
-   Para un intercambio X12 que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento ISA para la entidad como receptor del intercambio.  
  
-   Para un intercambio X12 que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento ISA.  
  
-   Para un intercambio EDIFACT que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento UNA para la entidad como receptor del intercambio.  
  
-   Para un intercambio EDIFACT que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento UNA.