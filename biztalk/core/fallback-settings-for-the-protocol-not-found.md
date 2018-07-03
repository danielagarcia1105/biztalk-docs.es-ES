---
title: Configuración de reserva para el protocolo no encontrado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13d703e9cd82dde0dc0da55a630f69f1b42903e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993125"
---
# <a name="fallback-settings-for-the-protocol-not-found"></a>No se encuentra la configuración de reserva para el protocolo
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                      AgreementResolutionFallbackSettingsNotFound                       |
|  Texto del mensaje   |                   Configuración de reserva para el {0} protocolo no encontrado.                    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta no se encontraba allí para el protocolo en particular.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, configure la configuración de reserva para el protocolo en particular.