---
title: 'De sesión único: Evento 10532 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 135060013686ff24e4f2692bda0e8829189e1c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974853"
---
# <a name="single-sign-on-event-10532"></a>De sesión único: Evento 10532
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                              Inicio de sesión único (SSO) empresarial                                                                              |
| Versión del producto |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    Identificador del evento     |                                                                                        10532                                                                                        |
|  Origen del evento   |                                                                                       ENTSSO                                                                                        |
|    Componente    |                                                                                         CO                                                                                          |
|  Nombre simbólico  |                                                                             SSO_WARN_LOST_SECRET_SERVER                                                                             |
|  Texto del mensaje   | No se pudieron recuperar los secretos principales. Compruebe si el nombre del servidor secreto principal es correcto y está disponible.%r<br /><br /> Nombre del servidor secreto: %1 %r<br /><br /> Código de error: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que la solicitud de obtención del secreto principal generó un error. Es posible que esto se deba a que el servicio Inicio de sesión único empresarial no está en ejecución en el servidor.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  

- Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.  

- Compruebe si el nombre de servidor secreto principal es correcto.  

- Compruebe si el servidor secreto principal está desconectado y si el servicio Inicio de sesión único empresarial está en ejecución.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
