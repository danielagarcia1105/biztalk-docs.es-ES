---
title: Separador de campos no se encuentra después del Id. de etiqueta de segmento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82511305a9df96af2bfafe81ce41fb0eaf9ab604
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965789"
---
# <a name="field-separator-not-found-after-segment-tag-id"></a>No se encontró el separador de campos después del Id. de etiqueta de segmento.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                          X12SeFsNotFoundAfterTagIdDescription                          |
|  Texto del mensaje   |                     No se encontró el separador de campos después del Id. de etiqueta de segmento.                     |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía un segmento que incluía un identificador de segmento sin separador de elementos de datos situado inmediatamente a continuación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que todos los identificadores de segmento del intercambio tengan separadores de elementos de datos situados inmediatamente a continuación de ellos y vuelva a enviar el intercambio.