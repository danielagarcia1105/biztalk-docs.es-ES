---
title: "Inicio de sesión único: Evento 10513 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1be7ae463dbb1ee9651f69f231614cc11db5f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10513"></a>Inicio de sesión único: Evento 10513
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10513|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_DB_FIRST_ACCESS|  
|Texto del mensaje|No se pudo ponerse en contacto con la base de datos SSO: %1 %r<br /><br /> %2 %r<br /><br /> Código de error: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que el servicio SSO no puede conectarse con la base de datos de SSO cuando se inicia. El mensaje de evento contiene la cadena de nombre de origen de datos (DSN) que indica los nombres de servidor SQL Server y de base de datos especificados, además del mensaje de error que se devolvió de las bibliotecas de conexión de SQL.  
  
 Cuando se inicie el servicio SSO, intentará conectarse con la base de datos de SSO mediante los nombres de servidor SQL Server y de base de datos especificados en el Registro. El servicio SSO intentará conectarse 12 veces, con cinco (5) segundos de espera entre cada intento con error, durante un total de un (1) minuto.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe que el servicio de SQL Server (MSSQLSERVER) se está ejecutando.  
  
-   Compruebe si es correcta la cadena de nombre de origen de datos (DSN) indicada en el mensaje de error y si contiene los nombres de servidor SQL Server y de base de datos.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)  
  
-   [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)  
  
-   [Configuración de SSO](../core/configuring-sso.md)  
  
-   SQL Server, Libros en pantalla