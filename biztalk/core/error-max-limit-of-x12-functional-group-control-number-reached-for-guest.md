---
title: El límite máximo aceptable X12 ha alcanzado el número de control de grupo funcional para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05cba774-fa35-4694-aa34-d7151f8cd75c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70855ad87ad18c29c51a4d87878339b014bb47d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010413"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-guest-settings"></a>Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional X12 en la configuración de Invitado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
| Versión del producto |                                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                           |
|    Identificador del evento     |                                                                                                       -                                                                                                       |
|  Origen del evento   |                                                            EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
|    Componente    |                                                                                                  Motor EDI                                                                                                   |
|  Nombre simbólico  |                                                                                          GlobalEdifactUnhNumberError                                                                                          |
|  Texto del mensaje   | Se ha alcanzado el límite máximo permitido para el número de control de grupo funcional X12 en la configuración de Invitado. Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo GS 6, del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de grupo del campo GS06 especificado en la configuración global era mayor que el valor máximo permitido. El número máximo de caracteres es 9 para el número de control de grupo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el número de control de grupo tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmentos GS y ST.  
  
2.  Haga clic en el campo Editar asociado con el campo GS06.  
  
3.  Defina el número de control de grupo en un valor nuevo, de modo que el campo tenga nueve dígitos o menos.