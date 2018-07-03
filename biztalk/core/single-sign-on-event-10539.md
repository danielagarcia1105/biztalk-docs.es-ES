---
title: 'De sesión único: Evento 10539 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7934b3011af2656f413270b4d249ca4f7f96bae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006286"
---
# <a name="single-sign-on-event-10539"></a>De sesión único: Evento 10539
## <a name="details"></a>Detalles  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10539                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                             CO                             |
|  Nombre simbólico  |              SSO_WARN_SSO_TICKETS_NOT_ALLOWED              |
|  Texto del mensaje   |        No se habilitaron vales para el sistema SSO.         |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no está habilitado el uso de vales de SSO. La posibilidad de permitir el uso de vales de SSO es una característica opcional del sistema SSO. Esta característica no se habilitó en el sistema SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver esta advertencia, haga lo siguiente:  

- Póngase en contacto con el administrador de SSO para habilitar vales para el sistema SSO. Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md)  

- [Uso de SSO](../core/using-sso.md)
