---
title: No se pudo leer el conjunto de delimitadores del intercambio (R2) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 778bfa7c417776e5baa78a6103e1075c7ccac27b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996277"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a>No se pudo leer el conjunto de delimitadores del intercambio (R2)
## <a name="details"></a>Detalles  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| Versión del producto |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                 |
|    Identificador del evento     |                                                             -                                                             |
|  Origen del evento   |                  EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
|    Componente    |                                                        Motor EDI                                                         |
|  Nombre simbólico  |                                                             -                                                             |
|  Texto del mensaje   | No se pudo leer el conjunto de delimitadores del intercambio. Falta el atributo DelimiterSetSerializedData en el nodo raíz. |

## <a name="explanation"></a>Explicación  
 Este error indica que el intercambio no contiene los valores del conjunto de delimitadores.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  

- Agregue valores del conjunto de delimitadores al intercambio, tal como se indica a continuación:  

  1.  Abra el mensaje.  

  2.  Determine si hay un segmento UNA en el intercambio. Si no hay ningún segmento UNA, pida al socio que lo agregue al intercambio.  

- Escriba los valores del delimitador en la propiedad de canalización EfactDelimiters, tal como se indica a continuación:  

  1. En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la ubicación de recepción o puerto de envío mediante la canalización para la que desee establecer las propiedades. Haga clic en **Propiedades**.  

  2. Haga clic en el botón de elipsis (…) junto a la canalización para la que desee establecer las propiedades.  

  3. Escriba valores para los delimitadores de UNA como una lista delimitada por comas (para UNA1, UNA2, UNA3, UNA4, UNA5 y UNA6), y cambie los valores predeterminados según sea necesario. Los valores predeterminados son los siguientes: 0x3A, 0x2B, 0x2C, 0x3F, 0 x 20, 0 x 27.  

  4. Haga clic en **Aceptar**.
