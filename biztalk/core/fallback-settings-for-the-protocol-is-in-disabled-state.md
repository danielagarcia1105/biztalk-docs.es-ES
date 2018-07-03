---
title: Configuración de reserva para el protocolo está en estado deshabilitado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1661aed16d2a63b158f3e1ae886b7dde381da14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983445"
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a>La configuración de reserva para el protocolo tiene el estado Deshabilitado
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                      AgreementResolutionFallbackSettingsDisabled                       |
|  Texto del mensaje   |              Configuración de reserva para el {0} protocolo está en estado deshabilitado.              |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server pudo resolver en un acuerdo y que se ha redireccionado a la configuración de reserva y se ha encontrado que ésta estaba en el estado deshabilitado para el protocolo en particular.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, habilite a la configuración de reserva para el protocolo en particular.