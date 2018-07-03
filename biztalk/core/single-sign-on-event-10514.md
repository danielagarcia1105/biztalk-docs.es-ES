---
title: 'De sesión único: Evento 10514 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b527841-a2e2-44c7-a9cb-6e9a8eea2fba
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fff4fbbb9b5c4d32968312b0f585ffbf2f5bb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995309"
---
# <a name="single-sign-on-event-10514"></a>De sesión único: Evento 10514
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                    Inicio de sesión único (SSO) empresarial                                                                                     |
| Versión del producto |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    Identificador del evento     |                                                                                              10514                                                                                               |
|  Origen del evento   |                                                                                              ENTSSO                                                                                              |
|    Componente    |                                                                                               N\D                                                                                                |
|  Nombre simbólico  |                                                                                       SSO_ERROR_DB_ACCESS                                                                                        |
|  Texto del mensaje   | Error al intentar obtener acceso a la base de datos de SSO.%r<br /><br /> Función: %1 %r<br /><br /> Archivo: %2 %r<br /><br /> %3.%r<br /><br /> Código de Error SQL: %4 %r<br /><br /> Código de error: %5 |
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que se recibió un error de SQL Server al intentar obtener acceso a la base de datos de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
- Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).  
  
- Compruebe el código de error de SQL Server mediante los eventos y el centro de mensajes de errores en [ http://go.microsoft.com/fwlink/?LinkID=20869 ](http://go.microsoft.com/fwlink/?LinkID=20869).  
  
  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)  
  
- [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)  
  
  Consulte, también, Libros en pantalla de SQL Server.