---
title: 'De sesión único: Evento 10522 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8bb97c8c537cca8b2f9c6e9176409d7da4dd3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972133"
---
# <a name="single-sign-on-event-10522"></a>De sesión único: Evento 10522
## <a name="details"></a>Detalles  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                   Inicio de sesión único (SSO) empresarial                                   |
| Versión del producto |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    Identificador del evento     |                                             10522                                             |
|  Origen del evento   |                                            ENTSSO                                             |
|    Componente    |                                              N\D                                              |
|  Nombre simbólico  |                                      SSO_ERROR_REENCRYPT                                      |
|  Texto del mensaje   | Error al volver a cifrar la base de datos de SSO. Vuelva a intentarlo en %1 minutos.%r<br /><br /> Código de error: %2 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que se produjo un error al volver a cifrar la base de datos de SSO. Cuando el servicio SSO se inicia en el servidor secreto principal, lo primero que hace es comprobar si la base de datos de SSO aún contiene información cifrada con el secreto principal anterior. Si es así, descifra esa información (mediante el secreto anterior) y vuelva a cifrarla mediante el secreto principal actual. Si, por cualquier motivo, el proceso genera un error, se emite este mensaje de evento.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe el código de error para determinar la causa del error. Podría ser un problema de red o base de datos. Si se trata de un problema intermitente, no es necesario realizar ninguna acción porque se volverá a intentar el recifrado tras un breve retardo. De lo contrario, detenga el servicio SSO e intente solucionar el problema. Una vez resuelto el problema, reinicie el servicio SSO, ya que el reinicio realizará el recifrado de forma automática.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)  

- [Servidor de secreto maestro](../core/master-secret-server.md)
