---
title: Alta disponibilidad para el servidor secreto principal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b99cb04-61a5-41cc-a409-35897c17b789
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9227715e30405217cdb9c13c2dc83dc0e236eef8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975853"
---
# <a name="high-availability-for-the-master-secret-server"></a>Alta disponibilidad para el servidor secreto principal
Incluso si no utiliza la funcionalidad de inicio de sesión único (SSO) empresarial para asignar credenciales e inicio de sesión único, SSO es una parte fundamental de la infraestructura global de Microsoft BizTalk Server, porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza SSO para ayudar a proteger la información de puerto configuración. Los datos de configuración de puerto se cifran y almacenan en la base de datos SSO. Cada servidor BizTalk server tiene un servicio de inicio de sesión único (ENTSSO.exe) que se usa para cifrar y descifrar los datos de configuración de puerto.  
  
 Cuando se inicia un servicio de inicio de sesión único, recupera la clave de cifrado desde el servidor secreto principal. Esta clave de cifrado se denomina el secreto principal. El servidor secreto principal es otro servicio de inicio de sesión único que tiene un subservicio adicional que mantiene y distribuye el secreto principal. Después de recupera un secreto principal, el servicio SSO almacena en caché. Cada 60 segundos, el servicio SSO sincroniza el secreto principal con el servidor secreto principal.  
  
 Si se produce un error en el servidor secreto principal y el servicio SSO detecta el error en uno de sus intervalos de actualización, el servicio de inicio de sesión único y todas las operaciones de tiempo de ejecución que se estaban ejecutando antes de que el servidor no se pudo, incluido el descifrado de credenciales, continúan correctamente. Sin embargo, no se pueden cifrar nuevas credenciales o datos de configuración de puerto. Por lo tanto, el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno tiene una dependencia en la disponibilidad del servidor secreto principal.  
  
## <a name="making-the-master-secret-server-available"></a>Hacer que el servidor secreto principal esté disponible  
 Para lograr una disponibilidad del sistema SSO y por lo tanto, de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, es fundamental realizar copias de seguridad del secreto principal en cuanto se genera. Si se pierde, se perderán también los datos que cifró el sistema SSO utilizando ese secreto principal. Para obtener más información sobre la seguridad del secreto principal de seguridad, consulte [cómo volver seguridad del secreto principal](http://go.microsoft.com/fwlink/?LinkID=151934) (<http://go.microsoft.com/fwlink/?LinkID=151934>) en la Ayuda de BizTalk Server.  
  
 Puede hacer que el servidor secreto principal esté disponible de dos maneras:  
  
- **Disponible, pero no una alta disponibilidad**. Puede crear un evento de Microsoft System Center Operations Manager para que le notifiquen cuando el servidor secreto principal deja de estar disponible y, a continuación, puede promover manualmente otro servidor de inicio de sesión único para el servidor secreto principal y restaurar el secreto principal en este servidor.  
  
   Aunque esta configuración no es de alta disponibilidad, puede ser satisfactoria para la mayoría de los escenarios y es coherente con el escalado horizontal de los hosts de procesamiento, envío y recepción.  
  
- **Alta disponibilidad**. para proporcionar redundancia al servidor secreto principal, utilice la Organización por clústeres de Windows en un clúster de servidores secretos principales diferente o configure el servidor secreto principal en un clúster de base de datos existente. Los servicios que proporciona el servidor secreto principal no consumen muchos recursos y, normalmente, no afectan a la funcionalidad de la base de datos ni al rendimiento si se instalan en un clúster de base de datos. La siguiente ilustración muestra cómo aportar alta disponibilidad al servidor secreto principal.  
  
   ![Servidor secreto principal de alta disponibilidad](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
   Aunque esta configuración tenga una alta disponibilidad, requiere recursos de hardware adicionales. Para obtener más información acerca de las opciones de instalación de alta disponibilidad para SSO, vea [opciones de instalación de SSO de alta disponibilidad](http://go.microsoft.com/fwlink/?LinkId=156838) (http://go.microsoft.com/fwlink/?LinkId=156838) en la Ayuda de BizTalk Server.  
  
   Esta sección incluye información detallada sobre cómo configurar el servidor secreto principal de SSO como recurso de clúster de alta disponibilidad en un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] clúster.  
  
  > [!NOTE]
  >  Para reducir los recursos de hardware para una solución de alta disponibilidad, puede agregar el servidor secreto principal como un recurso de clúster en su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster. Observe que no necesita comprar adicionales [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] licencias para instalar el inicio de sesión único de servicio en el equipo que ejecuta SQL Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Agrupación en clústeres del servidor de secreto maestro](../technical-guides/clustering-the-master-secret-server.md)  
  
-   [Designación manual de un nuevo servidor de secreto maestro](../technical-guides/designating-a-new-master-secret-server-manually.md)  
  
## <a name="see-also"></a>Vea también  
 [Planeación de alta disponibilidad2](../technical-guides/planning-for-high-availability2.md)   
 [Alta disponibilidad para Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)