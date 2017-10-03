---
title: "Inicio de sesión único: Evento 10511 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98371982-0db5-4ae0-9f92-f05a58e23b83
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c080812d70dc78a0fe2a9b217833f961da951401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10511"></a>Inicio de sesión único: Evento 10511
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10511|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_NO_DSN|  
|Texto del mensaje|No se encuentran los nombres de servidor SQL Server y de base de datos de SSO en el Registro. Use las herramientas de administración de SSO para configurar estos valores.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que no se encuentran los nombres de servidor SQL Server y de base de datos de SSO en el Registro. El servicio SSO necesita tal información para poder conectarse con la base de datos de SSO. Esta información se establece en el Registro durante la configuración. Por lo tanto, el evento indica que es posible que la configuración no se haya completado correctamente o que las entradas del Registro se eliminaron una vez completada la configuración.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Si sospecha que existe un error de configuración más grave, quite la configuración del producto y vuelva a configurarlo mediante el programa de configuración.  
  
-   Como alternativa, las entradas del Registro específicas faltantes se pueden establecer a través de la herramienta de línea de comandos de SSO "ssoconfig.exe" que se encuentra en el directorio de instalación de SSO (normalmente, C:\Archivos de programa\Archivos comunes\Inicio de sesión único empresarial). Es posible que el directorio de instalación de SSO sea diferente. Use la **- setDB** opción para establecer los nombres de base de datos de SQL Server y SSO necesarios.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)