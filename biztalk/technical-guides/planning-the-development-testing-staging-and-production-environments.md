---
title: Planear el desarrollo, pruebas, ensayo y entornos de producción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c83a42d-117f-4a24-a669-b3e4e1c9a056
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d72440595adb34b822b70e934985f88f79c66d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996053"
---
# <a name="planning-the-development-testing-staging-and-production-environments"></a>Planear el desarrollo, pruebas, ensayo y entornos de producción
En este tema se describe los entornos que se usa en el proceso de administración de versiones de una solución de BizTalk. Al igual que con cualquier solución de software empresarial, debe seguir las instrucciones de administración de versión de software establecido al desarrollar y lanzar una solución de BizTalk. Este proceso debe incluir las siguientes fases distintas:  
  
- Desarrollo  
  
- Las pruebas  
  
- Almacenamiento provisional  
  
- Production  
  
  Idealmente, debe completar cada fase en el proceso de administración de versiones en un entorno discreto, independiente de los otros entornos. De manera realista, es posible que deba combinar uno o varios de los entornos debido a hardware, tiempo u otras restricciones de recursos. Como mínimo debe separar el entorno de producción de los otros entornos.  
  
> [!NOTE]
>  Las instrucciones de instalación y actualización más recientes de BizTalk Server se enumeran en [de BizTalk Server lo que nuevo, instalación, configuración y actualización](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md). 
> 
> ##  <a name="BKMK_VirtualServ"></a> Uso de Virtual Server durante el proceso de administración de versiones  
>  Considere la posibilidad de completar el desarrollo, prueba unitaria y de ensayo en un entorno "virtual". Realizar el trabajo de desarrollo, pruebas unitarias y ensayo en un entorno virtual proporciona una gran flexibilidad y utiliza menos recursos de hardware de las necesarias en caso contrario. Si se usa un entorno virtual, debe asignar al menos 512 MB de memoria para cada máquina virtual que se ejecuta en el equipo host y 512 MB de memoria para el sistema operativo host adicionales.  
  
 Por ejemplo, para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno que usa cinco máquinas virtuales (dos equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], dos Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] nodos del clúster y un controlador de dominio), es conveniente sería planificar 3 GB de memoria instalada en el equipo host. Si el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno requiere más de 2 GB de memoria, considere la posibilidad de instalar una versión de 64 bits de Windows en el equipo host para asegurarse de que la cantidad máxima de memoria instalada es accesible por el sistema operativo host.  
  
> [!NOTE]
>  Para obtener recomendaciones sobre el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtual, consulte [Guía de Hyper-V de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkId=151834) (<http://go.microsoft.com/fwlink/?LinkId=151834>).  
> 
> [!NOTE]
>  BizTalk Server es totalmente compatible con un sistema operativo compatible que se ejecuta en el software de virtualización aparecen en la 842301 de artículo de Microsoft Knowledge Base [compatibilidad de Microsoft BizTalk Server en una máquina virtual](https://support.microsoft.com/kb/842301). Sin embargo, BizTalk Server no puede realizar según lo esperado si ha instalado en un sistema operativo compatible que se ejecuta en un software de virtualización que no sea el que se mencionan en el artículo de KB.  
  
## <a name="development-environment"></a>Entorno de desarrollo  
 Los proyectos de BizTalk que se usan para la solución de BizTalk se crean en el entorno de desarrollo. Debe instalar el software siguiente en los equipos utilizados en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno de desarrollo:  
  
- Servicios de Internet Information Server (IIS)  
  
- Visual Studio  
  
- Herramientas de cliente SQL Server  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (incluidos los componentes siguientes)  
  
  -   Documentación  
  
  -   Herramientas administrativas  
  
  -   SDK y herramientas de desarrollo  
  
  -   Software adicional  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], si la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son las bases de datos que alojarse localmente durante el desarrollo.  
  
- Normalmente, los desarrolladores deberían tener su propio equipo de desarrollo (físico o virtual) con el software necesario instalado.  
  
> [!NOTE]  
>  Se recomienda que comprar y usar la suscripción de Visual Studio para entornos que no sean de producción. Suscripciones de Visual Studio se ofrecen a un importante descuento del costo de una licencia comercial para el mismo software. Consulte [suscripciones de Visual Studio](https://visualstudio.com/subscriptions).  
  
## <a name="testing-environment"></a>Entorno de pruebas  
 Las pruebas unitarias pueden realizarse en un entorno virtual. Sin embargo, debe llevar a cabo el rendimiento de las pruebas en un entorno físico con el hardware y software que es idéntico al entorno de producción.  
  
 El entorno de pruebas se usa para medir las características de rendimiento como el rendimiento máximo sostenible (MST) y el rendimiento de seguimiento sostenible máximo de la solución de BizTalk. Por tanto debe coincidir el entorno de producción físico lo máximo posible. Para obtener más información acerca de la medición del rendimiento de las características de una solución de BizTalk vea [características de rendimiento del motor](../core/engine-performance-characteristics.md), o el [Guía de optimización de rendimiento de BizTalk Server](../technical-guides/biztalk-server-2010-performance-optimization-guide.md).
  
## <a name="staging-environment"></a>Entorno de ensayo  
 Utiliza normalmente el entorno de ensayo "pruebas unitarias" para la implementación real de la solución de BizTalk. El software instalado en el entorno de ensayo estrechamente debe coincidir con el software instalado en el entorno de producción. Sin embargo, puede, ser aceptable para utilizar equipos virtuales en el entorno de ensayo, puesto que este entorno no es se usa para medir el rendimiento. Para obtener más información sobre cómo implementar una aplicación de BizTalk en un entorno de ensayo, consulte [tareas de almacenamiento provisional para la implementación de la aplicación de BizTalk](../core/staging-tasks-for-biztalk-application-deployment.md).
  
## <a name="production-environment"></a>Entorno de producción  
 El entorno de producción es el entorno "activo" que se va a hospedar la solución de BizTalk en ejecución. El entorno de producción es el último punto de conexión en el proceso de administración de versiones y debería solo aplicaciones de BizTalk de host que previamente han experimentado desarrollo, pruebas unitarias, pruebas de carga y almacenamiento provisional en otros entornos. Unidad exhaustiva pruebas, las pruebas de carga y almacenamiento provisional con antelación will ayudan a garantizar el máximo rendimiento y tiempo de actividad de la aplicación de BizTalk en el entorno de producción.  
  
## <a name="guidelines-for-allocating-servers"></a>Directrices para la asignación de servidores  
 Las instrucciones siguientes proporcionan una regla general para el número de servidores de BizTalk y SQL Server, debe asignar a cada fase del proceso de administración de versión con un número determinado de equipos físicos de espera para su uso en producción: son aproximados estimaciones que están sujetos a cambios dependiendo de la arquitectura.  
  
> [!NOTE]  
>  Servidores virtuales pueden usarse en el desarrollo y en el entorno de ensayo y también se pueden usar para las pruebas unitarias. Todas las pruebas de rendimiento deben realizarse en el hardware físico que coincide con el hardware físico en el entorno de producción.  
  
|Equipos que ejecuten BizTalk Server utiliza en producción (se recomienda un hardware físico)|Servidores de desarrollo (hardware físico o virtual)|Servidores de prueba (se recomienda un hardware físico)|Servidores de ensayo (hardware físico o virtual)|Nº total. de los equipos que ejecutan BizTalk Server|  
|---|---|---|---|---|  
|1|2|1|1|5|  
|2|2|2|1|7|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
|No estimado. de los equipos que ejecutan SQL Server utilizada en producción (se recomienda un hardware físico)|Servidores de desarrollo (hardware físico o virtual)|Servidores de prueba (se recomienda un hardware físico)|Servidores de ensayo (hardware físico o virtual)|Nº total. de los equipos que ejecutan SQL Server|  
|---|---|---|---|---|  
|1|1|1|1|4|  
|2|1|2|1|6|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
## <a name="see-also"></a>Vea también  
 [Planificación del entorno de BizTalk Server](../technical-guides/planning-the-environment-for-biztalk-server.md)