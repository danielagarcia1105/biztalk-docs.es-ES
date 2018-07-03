---
title: El valor de propiedad flotante no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79327dc6-fc5e-4290-9663-16bb64970d4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7f0752a05b9e692a002c80332032337230decb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975077"
---
# <a name="the-float-property-value-is-not-valid"></a>El valor de propiedad flotante no es válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                    Motor de procesamiento por lotes                                     |
|  Nombre simbólico  |                               InvalidFloatPropertyValue                                |
|  Texto del mensaje   |                         El valor de propiedad flotante no es válido.                          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, indica que un valor especificado para una propiedad de una fila del cuadro de diálogo Filtro por lotes no era válido porque la propiedad requería un valor flotante y el valor especificado no lo era.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI. Asegúrese de que el valor especificado para una propiedad que requiera un valor flotante sea en realidad un flotante.