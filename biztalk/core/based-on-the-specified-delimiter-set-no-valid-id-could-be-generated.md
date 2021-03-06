---
title: Según el conjunto de delimitadores especificado, no pudo generarse ningún Id. válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ab5f018-b56f-4e3c-97e4-f9ea4258f6d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27cc4321826c824e93e43f94408bc08afc386ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005669"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-id-could-be-generated"></a>No pudo generarse ningún Id. válido según el conjunto de delimitadores especificado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| Versión del producto |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                        |
|    Identificador del evento     |                                                    -                                                    |
|  Origen del evento   |         EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]          |
|    Componente    |                                               Motor EDI                                                |
|  Nombre simbólico  |                                                    -                                                    |
|  Texto del mensaje   | No pudo generarse ningún Id. válido según el conjunto de delimitadores especificado. Utilice otro conjunto de delimitadores. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI no pudo generar un valor de identificador válido debido a que un carácter usado en el campo identificador del intercambio saliente era el mismo que un carácter separador.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie los valores de separador que la canalización de envío EDI usa para crear un mensaje de modo que ningún carácter separador sea el mismo que un carácter usado en un campo identificador del intercambio saliente. Realice una de las siguientes operaciones:  
  
-   Para un intercambio X12 que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento ISA para la entidad como receptor del intercambio.  
  
-   Para un intercambio X12 que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento ISA.  
  
-   Para un intercambio EDIFACT que se esté enviando a una entidad resuelta, cambie la configuración del separador en la página Definición de segmento UNA para la entidad como receptor del intercambio.  
  
-   Para un intercambio EDIFACT que se esté enviando a una entidad que no haya sido resuelta, cambie la configuración del separador en la página de propiedad global Definición de segmento UNA.