---
title: No se encuentra el tipo de espacio de nombres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b369b3ce29b989f01f0ea95d6f32a663d7e7bc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980774"
---
# <a name="type-cannot-be-found-in-namespace"></a>No se encuentra el tipo en el espacio de nombres
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                Error: Tipo de "{0}"no se encuentra en el espacio de nombres"{1}"                |
  
## <a name="explanation"></a>Explicación  
 Este error indica que los artefactos que se crean hacen referencias a tipos que no se encuentran en el espacio de nombres especificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Agregue una referencia que contenga el tipo que no se encuentra y vuelva a ejecutar el asistente (si es propietario del Servicio WCF que está intentando consumir). En caso contrario, póngase en contacto con el proveedor de servicios.