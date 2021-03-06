---
title: 'De sesión único: Evento 10501 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d615c01-4e80-4c40-ae15-fd1c48853474
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e45e8b471fb7e00dad84e30633dac11ea54e2ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011757"
---
# <a name="single-sign-on-event-10501"></a>De sesión único: Evento 10501
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                              Inicio de sesión único (SSO) empresarial                                                                                               |
| Versión del producto |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    Identificador del evento     |                                                                                                        10501                                                                                                         |
|  Origen del evento   |                                                                                                        ENTSSO                                                                                                        |
|    Componente    |                                                                                                         N\D                                                                                                          |
|  Nombre simbólico  |                                                                                              SSO_INFO_SERVICE_STARTING                                                                                               |
|  Texto del mensaje   | Se está iniciando el servicio SSO.%r<br /><br /> Nombre de equipo: %1 %r<br /><br /> Nombre de SQL Server: %2 %r<br /><br /> Nombre de la base de datos SSO: %3 %r<br /><br /> Uso de SSL. Cifrado de protocolo aplicado para conexiones de SQL Server. |

## <a name="explanation"></a>Explicación  
 Este evento de información indica que se está iniciado el servicio SSO con las propiedades de configuración especificadas.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar el evento de error, haga lo siguiente:  

- No se requiere ninguna acción.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Uso de SSO](../core/using-sso.md)
