---
title: Tipo de documento no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0676653df3124de72740a18c1d29b58f9282f684
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001853"
---
# <a name="doctype-is-invalid"></a>El tipo de documento no es válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| Versión del producto |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    Identificador del evento     |                                                        -                                                        |
|  Origen del evento   |             EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
|    Componente    |                                                   Motor EDI                                                    |
|  Nombre simbólico  |                                              DocTypeInvalidFormat                                               |
|  Texto del mensaje   | DOCTYPE {0} no es válido. No es posible determinar uno o más Id. de conjunto de transacciones, espacio de nombres o versión |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio entrante, pues el esquema no se ha descubierto correctamente.  
  
 Para X12, el espacio de nombres de destino viene determinado en la cuadrícula "Habilitar definiciones de conjuntos de transacciones personalizadas" de la página Propiedades de procesamiento de intercambio X12 del cuadro de diálogo Propiedades de EDI. Los valores de GS02 y ST01 del mensaje deben coincidir con los de una fila de la cuadrícula para poder identificar correctamente el espacio de nombres de destino. El nombre del esquema que debe usarse para el conjunto de transacciones se crea al agregar la versión (los cinco primeros caracteres de GS08) y el tipo de documento (ST01) del conjunto de transacciones entrantes al espacio de nombres de destino identificado.  
  
 Para EDIFACT, el espacio de nombres de destino viene determinado en la cuadrícula "Habilitar definiciones de conjuntos de transacciones personalizadas" de la página Propiedades de procesamiento de intercambio EDIFACT del cuadro de diálogo Propiedades de EDI. Los valores de UNH2.1, UNH2.2, UNH2.3, UNH2.5, UNG2.1 y UNG2.2 del mensaje deben coincidir con los de una fila de la cuadrícula para poder identificar correctamente el espacio de nombres de destino. El nombre del esquema que debe usarse para el conjunto de transacciones se crea al agregar el número de versión del mensaje en UNH2.2, el número de versión del mensaje en UNH2.3 y el tipo de mensaje en UNH2.1 del conjunto de transacciones entrantes al espacio de nombres de destino identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga lo siguiente:  
  
1.  Asegúrese de que el espacio de nombres para el esquema del conjunto de transacciones está correctamente identificado por una fila en la cuadrícula "Habilitar definiciones de conjuntos de transacciones personalizados" en la página Propiedades de procesamiento de intercambio del cuadro de diálogo Propiedades de EDI. Si no es así, cambie los valores en la cuadrícula.  
  
2.  Si el espacio de nombres se ha identificado correctamente, determine si los valores que se usan para identificar el esquema son correctos. Para X12, son la versión (los cinco primeros caracteres de GS08) y el tipo de documento (ST01) del conjunto de transacciones entrantes. Para EDIFACT, son el número de versión del mensaje en UNH2.2, el número de versión del mensaje en UNH2.3 y el tipo de mensaje en UNH2.1 en el conjunto de transacciones entrantes. Si los valores son incorrectos, pida al remitente del conjunto de transacciones que cambie los valores de dichos cambios y que reenvíe el mensaje.