---
title: Recomendaciones de seguridad de BizTalk Server en tiempo de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, runtime
- runtime, security
- discretionary access control lists (DACLs)
- DACLs
- .NET Framework Code Access Security Mechanism
ms.assetid: 1933789d-b79a-47ad-8f70-6f1e99bc2be0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f929e49a7c7bc94456262ca07a42bfdc02eb1107
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974189"
---
# <a name="biztalk-server-runtime-security-recommendations"></a>Recomendaciones de seguridad en tiempo de ejecución de BizTalk Server
Debe instalar el tiempo de ejecución de BizTalk Server, o el motor, en todos los equipos en los que desea recibir, enviar, procesar o realizar seguimiento de mensajes. Es decir, debe instalar los componentes de tiempo de ejecución en cualquier equipo en el que cree una instancia de host de BizTalk (servidores de procesamiento). Se recomienda seguir estas directrices para proteger e implementar el tiempo de ejecución de BizTalk Server en su entorno.  
  
- Asegúrese de que tiene los derechos de usuario de seguridad mínimos para realizar tareas de tiempo de ejecución de BizTalk. Para obtener más información acerca de los derechos de usuario de seguridad mínimos, vea [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).  
  
  > [!NOTE]
  >  La configuración de BizTalk proporciona a las cuentas los permisos mínimos que necesitan para realizar sus tareas.  
  
- La cuenta de servicio para cada instancia de host debe tener permisos para iniciar sesión como servicio en el equipo en el que se ejecuta la instancia de host.  
  
- Sólo la cuenta (o cuentas) de servicio de un host tienen acceso a los datos de cuadro de mensajes relacionados con un host y sólo esos servicios pueden exponer en el cuadro de mensajes. Para minimizar la posibilidad de ataques de revelación de información, no debería utilizar la misma cuenta de servicio para más de un host.  
  
- Los servidores de procesamiento (hosts que no realizan seguimiento) sólo necesitan conectarse a las bases de datos de cuadro de mensajes y de administración, y al servidor secreto principal. Si utiliza el protocolo de seguridad de Internet (IPSec), puede restringir el acceso de los servidores de procesamiento a estas dos bases de datos y al servidor secreto principal.  
  
- Todos los componentes que se ejecutan dentro del mismo host de BizTalk tienen el mismo nivel de confianza que el host. Al administrador de BizTalk le corresponde determinar qué componentes deben ejecutarse en el mismo host y, por tanto, compartir el mismo nivel de confianza. BizTalk se asegura de que sólo se ejecuten en un host de BizTalk los ensamblados que hayan instalado los administradores de BizTalk. Si desea crear más restricciones con respecto a los ensamblados que usa BizTalk, por ejemplo, si desea crear una restricción para que BizTalk solo ejecute ensamblados firmados por un proveedor determinado o valide la firma de nombre seguro de una orquestación, puede usar el Mecanismo de seguridad de acceso a código de [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]. Para obtener más información sobre el sitio Web de Microsoft MSDN en [ http://go.microsoft.com/fwlink/?LinkId=60947 ](http://go.microsoft.com/fwlink/?LinkId=60947).  
  
- El granularidad de autorización para envío de mensajes se encuentra en el nivel del host de BizTalk. Es decir, si tiene varias orquestaciones o adaptadores que se ejecutan dentro del mismo host de BizTalk, no puede restringir que una orquestación específica reciba mensajes enviados al host.  
  
- Cuando un host no está autorizado a recibir un mensaje, coloca ese mensaje en la cola de suspensión. De forma predeterminada, cuando en el mismo host se ejecutan adaptadores de recepción y orquestaciones, la orquestación puede leer la cola de suspensión del host. Entonces una orquestación puede seleccionar un mensaje que BizTalk dejó en suspenso debido a un error de autorización. Por lo tanto, se recomienda que no ejecute orquestaciones y adaptadores de recepción en el mismo host.  
  
- Las instancias de host son servicios de Windows que se ejecutan en un equipo específico. Para crear una instancia de host, debe ser administrador de BizTalk y administrador de Windows en el equipo en el que desea crear la instancia, dado que BizTalk crea un servicio de Windows que corresponda con la instancia de host.  
  
- Cuando Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] genera un ensamblado, usa una clave personalizada generada por el Entorno de desarrollo integrado (IDE). Si el entorno requiere la firma de todos los ensamblados con una clave específica, debe configurar el IDE para que todos los equipos de desarrollo usen esa clave o bien debe usar la firma retrasada de ensamblados.  
  
- Todos los componentes de las canalizaciones de recepción y envío intentan mantener la huella de memoria baja. Cuando los datos superan un umbral determinado, estos componentes envían datos a la carpeta temporal (%TEMP%) del disco. Debe asegurarse de que las carpetas temporales de las cuentas de servicio de las instancias de host tienen listas de control de acceso discrecional (DACL) adecuadas, de forma que sólo la cuenta de servicio pueda leer estos archivos. También debe asegurarse de que la carpeta temporal tiene espacio suficiente para almacenar los posibles archivos grandes.  
  
## <a name="see-also"></a>Vea también  
 [Administración de seguridad de BizTalk Server](../core/managing-biztalk-server-security.md)   
 [Puertos para los servidores de procesamiento](../core/ports-for-the-processing-servers.md)   
 [Recomendaciones de seguridad para una implementación de BizTalk Server](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [Planear la seguridad](../core/planning-for-security.md)