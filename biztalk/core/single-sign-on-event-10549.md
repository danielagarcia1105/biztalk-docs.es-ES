---
title: 'De sesión único: Evento 10549 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18a3b92192c7e7e4a0906bfd35e4069dd3481d45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993445"
---
# <a name="single-sign-on-event-10549"></a>De sesión único: Evento 10549
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                Inicio de sesión único (SSO) empresarial                                                                                 |
| Versión del producto |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    Identificador del evento     |                                                                                          10549                                                                                           |
|  Origen del evento   |                                                                                          ENTSSO                                                                                          |
|    Componente    |                                                                                            CO                                                                                            |
|  Nombre simbólico  |                                                                             SSO_ERROR_CREATE_DATABASE_FAILED                                                                             |
|  Texto del mensaje   | Error al crear e inicializar la base de datos de SSO.%r<br /><br /> Nombre de SQL Server: %1 %r<br /><br /> Nombre de la base de datos SSO: %2 %r<br /><br /> Usuario cliente: %3 %r<br /><br /> Código de error: %4 |

## <a name="explanation"></a>Explicación  
 Este error indica que no se pudo crear e inicializar la base de datos de SSO.  

## <a name="user-action"></a>Acción del usuario  
 Para solucionar el error, haga lo siguiente:  

- Compruebe si en los registros de eventos del sistema y la aplicación existen mensajes asociados.  

- Vuelva a ejecutar el programa de instalación.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Instalación de SSO](../core/installing-sso.md)
