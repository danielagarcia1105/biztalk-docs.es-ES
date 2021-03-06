---
title: El límite máximo aceptable X12 ha alcanzado el número de control de intercambio para la configuración de invitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1145573dc5aec674e79cef960c4737ddfe6d5e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005957"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a>Se ha alcanzado el límite máximo permitido para el número de control de intercambio X12 en la configuración de Invitado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| Versión del producto |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    Identificador del evento     |                                                                                                     -                                                                                                      |
|  Origen del evento   |                                                           EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
|    Componente    |                                                                                                 Motor EDI                                                                                                 |
|  Nombre simbólico  |                                                                                          GlobalX12IsaNumberError                                                                                           |
|  Texto del mensaje   | Se ha alcanzado el límite máximo permitido para el número de control de intercambio X12 en la configuración de Invitado. Para restablecer el contador, desplácese hasta la pantalla de función de remitente de configuración global, campo ISA 13, del administrador de acuerdos de socios comerciales. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el intercambio X12 saliente porque el número de control de intercambio del campo ISA13 especificado en la configuración global era mayor que el valor máximo permitido. El número máximo de caracteres es nueve para el número de control de intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, restablezca el número de control de intercambio tal como se indica a continuación:  
  
1.  En el cuadro de diálogo Propiedades globales de EDI, abra la página Definición de segmento ISA.  
  
2.  Haga clic en el campo Editar asociado con el campo ISA13.  
  
3.  Defina el número de control de intercambio en un valor nuevo, de modo que el campo tenga un número de dígitos aceptable.