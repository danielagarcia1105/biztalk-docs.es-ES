---
title: Esquema de control debería tener segmentos de encabezado en el orden correcto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c86b8d66526c0406faedeac0aedbbe0e1b270ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967925"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a>El esquema de control debería tener segmentos de encabezado en el orden correcto
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |  Esquema de control debería tener segmentos en el orden siguiente: ISA GS ST... SE GE IEA  |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio entrante porque los encabezados y finalizadores del intercambio, de los grupos y de los conjuntos de transacciones no se encontraban en el orden correcto en el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los encabezados ISA, GS y ST, y que los finalizadores SE, GE e IEA, se encuentran en el orden correcto en el intercambio y, a continuación, vuelva a enviar el intercambio.