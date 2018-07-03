---
title: Elemento de datos demasiado corto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22c0551-3262-476c-a6c6-2fd214331244
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db14770404a45ddbfd3aea6ed71e9b8b22417515
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005301"
---
# <a name="data-element-too-short"></a>Elemento de datos demasiado corto.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                                 Elemento de datos demasiado corto.                                 |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción de EDI o la canalización de envío de EDI no pudo procesar el intercambio entrante porque un elemento de datos tenía una longitud menor que la mínima que especifica el esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, aumente de tamaño el elemento de datos del intercambio que era demasiado corto de modo que supere la longitud mínima. Para determinar la longitud mínima, abra el esquema en la carpeta \XSD_Schema, busque en el identificador del elemento de datos e identifique cuál es el valor de minLength.