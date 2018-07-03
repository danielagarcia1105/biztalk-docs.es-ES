---
title: No es válido el valor de propiedad bytes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef443c74c47883d04bcad2c1da5bb9423f7c01d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977855"
---
# <a name="the-byte-property-value-is-not-valid"></a>El valor de la propiedad en bytes no es válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                    Motor de procesamiento por lotes                                     |
|  Nombre simbólico  |                                InvalidBytePropertyValue                                |
|  Texto del mensaje   |                          El valor de la propiedad en bytes no es válido.                          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido, pues la propiedad requería un valor en bytes y el valor especificado no lo era.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI. Asegúrese de que el valor especificado para una propiedad que requiera un valor en bytes sea en realidad en bytes.