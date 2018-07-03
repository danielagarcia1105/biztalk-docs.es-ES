---
title: El límite máximo aceptable X12 ha alcanzado el número de control de grupo funcional para la entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a920a66c-1e38-4f4a-8113-cbad01940839
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527f6709d48124f7ffcc0823bdc5ff84e92256ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978405"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-party"></a>Se ha alcanzado el límite máximo permitido del número de control de grupo funcional X12 para la entidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| Versión del producto |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    Identificador del evento     |                                                                                              -                                                                                               |
|  Origen del evento   |                                                    EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                    |
|    Componente    |                                                                                          Motor EDI                                                                                          |
|  Nombre simbólico  |                                                                                    PartyX12GsNumberError                                                                                     |
|  Texto del mensaje   | El límite máximo aceptable X12 ha alcanzado el número de control de grupo funcional para la entidad {0}. Para restablecer el contador, desplácese hasta Entidad, en la pantalla de función del destinatario, campo GS 6, del administrador de acuerdos de socios comerciales |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de grupo del campo GS06 especificado en la configuración de entidad era mayor que el valor máximo permitido. El número máximo de caracteres es 9 para el número de control de grupo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el número de control de grupo tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades de EDI para la entidad resuelta para el intercambio, abra la página Definición de segmentos GS y ST para la entidad como receptor de intercambio.  
  
2.  Haga clic en el campo Editar asociado con el campo GS06.  
  
3.  Defina el número de control de grupo en un valor nuevo, de modo que el campo tenga nueve dígitos o menos.