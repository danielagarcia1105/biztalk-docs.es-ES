---
title: Entre la infracción de regla de validación de campos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d590fc318e7d833a067f4275986bef88da10364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976661"
---
# <a name="cross-field-validation-rule-violated"></a>Infracción de regla de validación de campos cruzados.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                          Infracción de regla de validación de campos cruzados.                          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el intercambio X12 tuvo un error de validación de campo cruzado en la canalización de recepción o de envío. Esto indica que el indicador X12ConditionDesignator_Check está configurado en "Yes" y que al menos un elemento del intercambio tuvo un error en una regla identificada por el prefijo "X12ConditionDesignatorX".  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Identifique qué elemento de datos no ha superado una regla de validación de campo cruzado. Póngase en contacto con el remitente del intercambio e indique que debe seguirse la regla al crear el intercambio.  
  
-   Abra el esquema para el intercambio y establezca en "No" el indicador X12ConditionDesignator_Check para el elemento de datos que no ha superado la validación.