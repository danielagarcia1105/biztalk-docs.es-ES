---
title: Separador de elementos de datos no válidos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c50a8b-274f-4f4a-9826-4f6f8123e9d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fbc355c6a89bd69364200dcd20ca257fc9dc54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972597"
---
# <a name="invalid-data-element-separator"></a>Separador de elemento de datos no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                      X12Ta1InvalidDataElementSeparatorDescription                      |
|  Texto del mensaje   |                             Separador de elemento de datos no válido.                             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del terminador de segmento del intercambio no estaba limitado a los caracteres del juego de caracteres ASCII. En X12, el terminador de segmento se define como el cuarto carácter del segmento ISA. En EDIFACT, el terminador de segmento es el campo UNA2.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el terminador de segmento (el cuarto carácter del segmento ISA de un intercambio X12 o el campo UNA2 en un intercambio EDIFACT) está limitado a los caracteres del conjunto de caracteres ASCII. Vuelva a enviar el intercambio.