---
title: El esquema no contiene el elemento raíz | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2191a5d9ea891efa285d8fc5006f243319fde5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008445"
---
# <a name="the-schema-does-not-contain-the-root-element"></a>El esquema no contiene el elemento raíz
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                             SchemaCode102ENullRootElement                              |
|  Texto del mensaje   |                    El esquema no contiene el elemento raíz {0}                    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el mensaje entrante o que la canalización de envío no pudo procesar el mensaje saliente porque el esquema usado para validar el mensaje no contenía el elemento raíz.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, anule la implementación del esquema del documento, agregue el elemento raíz al esquema y vuelva a implementar el esquema.