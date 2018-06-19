---
title: 'Inicio de sesión único: Evento 10514 | Documentos de Microsoft'
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
ms.openlocfilehash: 40077ead4157b4cc6c91a2c44b4a19569d76ebc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270508"
---
# <a name="single-sign-on-event-10514"></a>Inicio de sesión único: Evento 10514
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10514|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_DB_ACCESS|  
|Texto del mensaje|Error al intentar obtener acceso a la base de datos de SSO.%r<br /><br /> Función: %1 %r<br /><br /> Archivo: %2 %r<br /><br /> %3.%r<br /><br /> Código de Error SQL: %4 %r<br /><br /> Código de error: %5|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que se recibió un error de SQL Server al intentar obtener acceso a la base de datos de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe que se está ejecutando el servicio SQL Server (MSSQLSERVER).  
  
-   Compruebe el código de error de SQL Server mediante los eventos y Errors Message Center en [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)  
  
-   [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)  
  
 Consulte, también, Libros en pantalla de SQL Server.