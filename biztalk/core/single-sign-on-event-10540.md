---
title: 'De sesión único: Evento 10540 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1bcd7cc64a79634aa7868791d7e74e92cd1c4a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990949"
---
# <a name="single-sign-on-event-10540"></a>De sesión único: Evento 10540
## <a name="details"></a>Detalles  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  Nombre del producto   |                            Inicio de sesión único (SSO) empresarial                             |
| Versión del producto |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    Identificador del evento     |                                      10540                                       |
|  Origen del evento   |                                      ENTSSO                                      |
|    Componente    |                                        CO                                        |
|  Nombre simbólico  |                         SSO_WARN_APP_TICKETS_NOT_ALLOWED                         |
|  Texto del mensaje   | No se habilitaron vales para la aplicación.%r<br /><br /> Nombre de la aplicación: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se habilitó la característica de vales para la aplicación. El uso de vales de SSO es una característica opcional para cada aplicación de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Póngase en contacto con el administrador de aplicaciones para habilitar vales para el sistema SSO. Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Vales de SSO](../core/sso-tickets.md)  

- [Cómo enumerar las propiedades de una aplicación afiliada](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [Cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md)
