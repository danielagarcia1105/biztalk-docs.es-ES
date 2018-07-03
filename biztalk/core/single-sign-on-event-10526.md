---
title: 'De sesión único: Evento 10526 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f72d466-8b63-453c-b608-f9d64f635f65
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 433190146391c494ff3b890c8332cc15fb947753
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024458"
---
# <a name="single-sign-on-event-10526"></a>De sesión único: Evento 10526
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                     Inicio de sesión único (SSO) empresarial                                                                     |
| Versión del producto |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    Identificador del evento     |                                                                               10526                                                                               |
|  Origen del evento   |                                                                              ENTSSO                                                                               |
|    Componente    |                                                                                N\D                                                                                |
|  Nombre simbólico  |                                                                 SSO_ERROR_GENERATE_SECRET_FAILED                                                                  |
|  Texto del mensaje   | No se pudo generar un secreto principal nuevo.%r<br /><br /> Usuario cliente: %1 %r<br /><br /> Equipo cliente: %2%r<br /><br /> Id. de seguimiento: %3 %r<br /><br /> Código de error: %4 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que no se puedo llevar a cabo el intento de generar un secreto principal nuevo por parte del usuario. Esto puede deberse a problemas de permisos (se debe ser un administrador de SSO para generar el secreto principal) o a problemas durante la escritura del secreto principal en el archivo de copia de seguridad. En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  

- Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.  

- Compruebe si dispone de los permisos de administrador de SSO correspondientes.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Cómo generar el secreto principal](../core/how-to-generate-the-master-secret.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)
