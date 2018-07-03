---
title: 'De sesión único: Evento 10515 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c3d7498bcd6a045936103d682d3643761a182c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980821"
---
# <a name="single-sign-on-event-10515"></a>De sesión único: Evento 10515
## <a name="details"></a>Detalles  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  Nombre del producto   |                           Inicio de sesión único (SSO) empresarial                           |
| Versión del producto |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    Identificador del evento     |                                     10515                                     |
|  Origen del evento   |                                    ENTSSO                                     |
|    Componente    |                                      N\D                                      |
|  Nombre simbólico  |                            SSO_ERROR_POLL_DATABASE                            |
|  Texto del mensaje   | Se interrumpió la comunicación con la base de datos de SSO. Compruebe si la base de datos de SSO está disponible. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que se interrumpió la comunicación entre el servicio SSO y la base de datos de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
- Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).  
  
- Compruebe la conectividad de red con SQL Server si se encuentra en un servidor remoto.  
  
  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)  
  
- [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)  
  
- [Configuración de SSO](../core/configuring-sso.md)  
  
  También vea Libros en pantalla de SQL Server