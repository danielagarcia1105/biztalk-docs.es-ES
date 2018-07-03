---
title: Separador de elementos de componente no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 738a1107-86e6-4475-a61d-ed1d9ab7e5d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 927a33124fdb624df79d3b2f99b07f61345289e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997557"
---
# <a name="invalid-component-element-separator"></a>Separador de elemento de componente no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                   X12Ta1InvalidComponentElementSeparatorDescription\                   |
|  Texto del mensaje   |                          Separador de elemento de componente no válido.                           |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del separador de componentes del intercambio no estaba limitado a los caracteres del juego de caracteres ASCII. En X12, el terminador de segmento es el campo ISA6. En EDIFACT, el terminador de segmento es el campo UNA1.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el terminador de segmento (el campo ISA16 de un intercambio X12 o el campo UNA1 de un intercambio EDIFACT) está limitado a los caracteres del juego de caracteres ASCII. Vuelva a enviar el intercambio.