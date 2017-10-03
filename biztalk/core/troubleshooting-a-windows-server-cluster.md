---
title: "Solución de problemas de un clúster de servidores de Windows | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 283cf4cd-ce40-48b7-8549-9ab17d7d2c34
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da1159bafc42f6cfbf47621e3b846764e50e5267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-a-windows-server-cluster"></a>Solución de problemas de un clúster de servidores de Windows
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite el uso del clúster de Windows Server para la funcionalidad de clúster de hosts con el fin de proporcionar alta disponibilidad para el servidor secreto principal de inicio de sesión único (SSO) empresarial, así como para las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este tema proporciona directrices generales para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de clúster de Windows Server y trata algunos problemas conocidos que pueden producirse al utilizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de clúster de Windows Server.  
  
## <a name="general-guidelines"></a>Directrices generales  
 Siga estas directrices generales para maximizar la productividad con el clúster de Windows Server y para solucionar problemas en el clúster de Windows Server que pueden afectar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
1.  Realice el trabajo de prueba de concepto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con un clúster de Windows Server en un entorno de servidor virtualizado.  
  
     **El rol de Hyper-V disponible con Windows Server 2008 puede utilizarse para crear un entorno de servidor virtualizado.**  
  
    -   Para obtener más información acerca de Windows Server 2008 Hyper-V, vea "Virtualización y consolidación" en [http://go.microsoft.com/fwlink/?LinkID=121187](http://go.microsoft.com/fwlink/?LinkID=121187).  
  
    -   Para obtener información detallada acerca de las ventajas de aprovechar la tecnología de virtualización con Hyper-V, vea las notas del producto "Avanzada virtualización ventajas de Windows Server 2008 ediciones para the Enterprise" disponible para su descarga en [ http://go.Microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530).  
  
    -   Pasos para usar Hyper-V para crear un clúster de Windows Server 2008 están disponibles en [http://go.microsoft.com/fwlink/?LinkId=129680](http://go.microsoft.com/fwlink/?LinkId=129680).  
  
     Al realizar el trabajo de prueba de concepto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con un clúster de Windows Server en un entorno de servidor virtual, se consigue una gran flexibilidad y se usan menos recursos de hardware que los necesarios para un clúster de Windows Server. Si va a seguir este enfoque, asigne al menos 512 MB de memoria a cada equipo virtual que funcione de forma simultánea en el equipo host, así como otros 512 MB de memoria adicional para el sistema operativo host. Por ejemplo, para una solución [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con un clúster de Windows Server que use cinco equipos virtuales (dos nodos de clúster de BizTalk Server, dos nodos de clúster de Microsoft SQL Server y un controlador de dominio), lo conveniente sería planificar 3 GB de memoria instalada en el equipo host. Si el entorno de prueba de concepto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita más de 2 GB de memoria, considere la posibilidad de instalar una versión de 64 bits de Windows en el equipo host (necesario para el rol Hyper-V) para asegurarse de que el sistema operativo host pueda tener acceso a toda la memoria instalada.  
  
## <a name="troubleshooting-resources"></a>Recursos para la solución de problemas  
 **Recursos para solucionar problemas de clústeres de conmutación por error de Windows Server 2008**  
  
-   Revise el [validación de clúster de conmutación por error y solución de problemas con Windows Server 2008](http://go.microsoft.com/fwlink/?LinkId=129729) Webcast de TechNet en el sitio Web de Microsoft TechNet. Esta difusión por web describe cómo resolver la validación de clúster de conmutación por error y cómo solucionar problemas con Windows Server 2008.  
  
-   Para obtener más información acerca del análisis de problemas con los clústeres de conmutación por error de Windows Server 2008, revise el tema [ver eventos y registros para un clúster de conmutación por error](http://go.microsoft.com/fwlink/?LinkId=129730) en el sitio Web de Microsoft TechNet.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="any-attempt-to-bring-a-clustered-msdtc-resource-online-fails-which-causes-dependent-biztalk-server-services-to-fail"></a>Se producen errores en los intentos de conectar un recurso MSDTC agrupado que hacen que se produzcan errores en los servicios dependientes de BizTalk Server.  
  
##### <a name="problem"></a>Problema  
 Un recurso Coordinador de transacciones distribuidas (MSDTC) agrupado no se puede poner en línea a través de la **poner en línea** opción en el Administrador de clústeres, lo que hace que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operaciones de tiempo de ejecución que son dependientes de MSDTC compatibilidad con transacciones a un error.  
  
##### <a name="cause"></a>Causa  
 Existen varios motivos por los que se producen errores en el recurso MSDTC agrupado, entre los que se incluyen los siguientes:  
  
-   El recurso MSDTC agrupado no está configurado con las dependencias de recurso Disco y Nombre de red correctas o bien se producen errores en éstas.  
  
-   Los problemas de permisos impiden que el recurso MSDTC agrupado se active.  
  
##### <a name="resolution"></a>Solución  
 **Complete los pasos siguientes en un clúster de Windows Server 2008:**  
  
-   Siga los pasos de [lista de comprobación: crear un MS DTC Resource en un clúster de conmutación por error de Windows Server 2008](http://go.microsoft.com/fwlink/?LinkId=129677) para crear uno o varios recursos en clúster de MSDTC en un clúster de conmutación por error de Windows Server 2008.  
  
## <a name="see-also"></a>Vea también  
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)   
 [Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [Opciones de instalación de SSO de alta disponibilidad](../core/high-availability-sso-installation-options.md)