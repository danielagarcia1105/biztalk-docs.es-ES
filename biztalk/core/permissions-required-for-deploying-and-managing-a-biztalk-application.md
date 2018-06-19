---
title: Permisos necesarios para implementar y administrar una aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], security
- permissions, EDI adapters
- deploying, security
- security, applications
- security, EDI adapters
- assemblies, permissions
- permissions, deploying
- EDI adapters, security
- permissions, assemblies
- security, assemblies
- permissions, applications
- deploying, permissions
- applications, importing
- applications, exporting
- permissions, exporting
- installing, permissions
- applications, security
- security, permissions
- applications, installing
- assemblies, security
- managing, security
ms.assetid: 4a459ff1-661d-403a-99e0-d54b82e008d0
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 608da93cd1960d26304f4dcebe239367de2404e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265548"
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a>Permisos necesarios para la implementación y administración de aplicaciones de BizTalk
La implementación de aplicaciones incluye la implementación de ensamblados de BizTalk a partir de Visual Studio, así como la importación, exportación e instalación de aplicaciones de BizTalk. Los permisos básicos necesarios para llevar a cabo estas tareas son los siguientes:  
  
-   Como miembro del grupo de administradores de BizTalk Server, se le conceden los permisos necesarios para implementar ensamblados de BizTalk a partir de Visual Studio.  
  
-   Como miembro del grupo de administradores de BizTalk Server, se le conceden los permisos necesarios para implementar ensamblados de BizTalk en un grupo de BizTalk. Si se ha especificado la opción para agregar un ensamblado incluido en la aplicación a la caché de ensamblados global (GAC), también es preciso contar con permisos de escritura en la carpeta de ensamblados. Como miembro del grupo de administradores locales, cuenta con este permiso.  
  
-   Como miembro del grupo de administradores de BizTalk Server o de operadores de BizTalk Server, se le conceden los permisos necesarios para:  
  
    -   Exportar aplicaciones de BizTalk.  
  
    -   Iniciar y detener puertos de envío, grupos de puertos de envío y orquestaciones.  
  
    -   Habilitar y deshabilitar ubicaciones de recepción.  
  
    -   Suspender, reanudar y finalizar instancias.  
  
    -   Iniciar y detener aplicaciones.  
  
-   Como miembro del grupo local de administradores, se le conceden permisos para instalar aplicaciones de BizTalk en el equipo local.  
  
 Es posible que desee asignar los permisos más restrictivos a los usuarios para que lleven a cabo estas tareas. El resto de este tema proporciona más detalles sobre los permisos necesarios con el contenido y orden siguientes:  
  
-   [Permisos para implementar ensamblados de BizTalk desde Visual Studio](#BKMK_Permissions_for_deploying)  
  
-   [Permisos para la importación de una aplicación](#BKMK_Permissions_for_importing)  
  
-   [Permisos para exportar una aplicación](#BKMK_Permissions_for_exporting)  
  
-   [Permisos para la instalación de una aplicación](#BKMK_Permissions_for_installing_an_application)  
  
##  <a name="BKMK_Permissions_for_deploying"></a>Permisos para implementar ensamblados de BizTalk desde Visual Studio  
 Para implementar ensamblados de BizTalk desde Visual Studio, debe contar, como mínimo, con permisos de escritura en la base de datos de administración de BizTalk. Este permiso se le concede como miembro del grupo de administradores de BizTalk Server.  
  
##  <a name="BKMK_Permissions_for_importing"></a>Permisos para la importación de una aplicación  
 Para importar una aplicación de BizTalk, debe contar, como mínimo, con los siguientes permisos. Todos los permisos necesarios se le conceden como miembro del grupo de administradores de BizTalk Server; no obstante, si desea instalar cualquier ensamblado en la GAC, también debe contar con permisos de escritura en la carpeta de ensamblados.  
  
|Elemento|Permissions|Caso en el que resulta necesario|  
|----------|-----------------|-------------------|  
|Base de datos de administración de BizTalk|Lectura/escritura|Siempre.|  
|Base de datos del motor de reglas de BizTalk|Lectura/escritura|Necesario únicamente si la aplicación incluye recursos de reglas.|  
|Base de datos de BAM|Lectura/escritura|Necesario únicamente si la aplicación incluye recursos de BAM.|  
|Caché de ensamblados global (GAC)|Lectura/escritura|Requerido únicamente si la aplicación incluye recursos de ensamblados y se especifica que los ensamblados se agregan a la GAC durante la importación. (Consulte la siguiente nota.)|  
  
> [!NOTE]
>  Al importar un ensamblado utilizando el asistente para importación, se puede especificar la opción para agregar el ensamblado a la caché de ensamblados global (GAC). En este caso, es necesario contar con permisos de escritura en la carpeta de ensamblados. Para obtener más información acerca de la carpeta de ensamblados, vea [permisos para la instalación de una aplicación](#BKMK_Permissions_for_installing_an_application).  
>   
>  Si la aplicación incluye una secuencia de comandos que implementa cualquier elemento además de los enumerados, es necesario contar con permisos adecuados para implementar los elementos adicionales.  
  
##  <a name="BKMK_Permissions_for_exporting"></a>Permisos para exportar una aplicación  
 Para exportar una aplicación de BizTalk, debe contar, como mínimo, con los siguientes permisos. Los permisos necesarios se le conceden como miembro del grupo de operadores de BizTalk.  
  
|Elemento|Permissions|Caso en el que resulta necesario|  
|----------|-----------------|-------------------|  
|Base de datos de administración de BizTalk|Lectura|Siempre.|  
|Base de datos del motor de reglas de BizTalk|Lectura|Necesario únicamente si la aplicación incluye recursos de reglas.|  
|Almacén de certificados|Lectura|Necesario únicamente si la aplicación incluye recursos de certificados.|  
|Internet Information Services|Lectura|Necesario únicamente si la aplicación incluye recursos del directorio virtual.|  
  
##  <a name="BKMK_Permissions_for_installing_an_application"></a>Permisos para la instalación de una aplicación  
 De forma predeterminada, los miembros del grupo local de administradores cuentan con los permisos necesarios para instalar aplicaciones de BizTalk en el equipo local. Si desea proporcionar permisos más restringidos a los usuarios que necesiten instalar aplicaciones, consulte la tabla siguiente en la que se proporcionan los permisos mínimos que debe configurar. Además de estos permisos, si la aplicación tiene recursos que requieren permisos adicionales para su instalación, como para crear una nueva tabla de base de datos o una nueva base de datos, también debe contar con estos permisos.  
  
|Elemento|Permissions|Caso en el que resulta necesario|  
|----------|-----------------|-------------------|  
|Almacén de certificados|Lectura/escritura|Necesario únicamente si la aplicación incluye recursos de certificados.|  
|Internet Information Services|Lectura/escritura|Necesario únicamente si la aplicación incluye recursos del directorio virtual.|  
|GAC|Lectura/escritura|Necesario únicamente si la aplicación incluye recursos de ensamblados y se especifica que los ensamblados se agregan a la GAC durante la instalación. (Vea la nota, debajo).|  
|Sistema de archivos|Lectura/escritura|Necesario únicamente si se ha establecido una propiedad de destino para un recurso.|  
|Registro|Lectura/escritura|Obligatorio si la **regsvcs** o **regasm**propiedad está establecida en True para un recurso de ensamblado que contiene componentes de COM o COM + administrados.|  
|Registro|Lectura/escritura|Necesario si la aplicación incluye recursos COM sin administrar.|  
  
> [!NOTE]
>  En la consola de administración de BizTalk Server, se puede especificar la agregación de un ensamblado a la GAC durante la instalación (haga clic con el botón secundario en el ensamblado de la carpeta de recursos y, a continuación, haga clic en Modificar). Si se especifica esta opción, la instalación de la aplicación de BizTalk requerirá permiso de escritura en la carpeta de ensamblados, que es la que contiene la GAC. La ruta de la carpeta de ensamblados es %SystemRoot%\assembly.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de seguridad para la implementación de aplicaciones](../core/security-considerations-for-application-deployment.md)