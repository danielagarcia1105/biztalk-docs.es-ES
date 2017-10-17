---
title: "Planear el desarrollo, pruebas, ensayo y entornos de producción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c83a42d-117f-4a24-a669-b3e4e1c9a056
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5572ab96215d07570a39f53009eae3038792db8
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="planning-the-development-testing-staging-and-production-environments"></a>Planear el desarrollo, pruebas, ensayo y entornos de producción
Este tema describen los entornos que se utiliza en el proceso de administración de versión para una solución de BizTalk. Al igual que con cualquier solución de software empresarial, debe seguir directrices para la administración de versión de software establecido cuando se desarrollan y la versión de una solución de BizTalk. Este proceso debe incluir las siguientes fases distintas:  
  
-   Desarrollo de  
  
-   Pruebas  
  
-   Almacenamiento provisional  
  
-   Production  
  
 Idealmente, debe completar cada fase en el proceso de administración de versión en un entorno discreto, independiente de los otros dos entornos. En la práctica, tendrá que combinar uno o varios de los entornos debido a hardware, el tiempo u otras restricciones de recursos. Como mínimo debe separar el entorno de producción de los otros dos entornos.  
  
> [!NOTE]  
>  Las instrucciones de instalación y la actualización más recientes para BizTalk Server se enumeran en [de BizTalk Server lo que nuevo, instalación, configuración y actualización](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md). 
>  
##  <a name="BKMK_VirtualServ"></a>Utilizando servidor Virtual durante el proceso de administración de versión  
 Considere la posibilidad de completar el desarrollo, la prueba unitaria y de ensayo en un entorno "virtual". Realizar el trabajo de desarrollo, pruebas unitarias y almacenamiento provisional en un entorno virtual consigue una gran flexibilidad y utiliza menos recursos de hardware que lo requerido en caso contrario. Si se usa un entorno virtual, debe asignar al menos 512 MB de memoria para cada máquina virtual que se ejecuta en el equipo host y otros 512 MB de memoria para el sistema operativo host.  
  
 Por ejemplo, para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno que use cinco equipos virtuales (dos equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], dos Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] nodos del clúster y un controlador de dominio), lo conveniente sería planificar 3 GB de memoria instalada en el equipo host. Si el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno requiere más de 2 GB de memoria, considere la posibilidad de instalar una versión de 64 bits de Windows en el equipo host para asegurarse de que la cantidad máxima de memoria instalada está accesible para el sistema operativo host.  
  
> [!NOTE]  
>  Para obtener recomendaciones sobre el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtual, vea [Guía de Hyper-V de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkId=151834) (http://go.microsoft.com/fwlink/?LinkId=151834).  
  
> [!NOTE]  
>  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]es totalmente compatible en un sistema operativo compatible que se ejecuta en el software de virtualización aparecen en la 842301 de artículo de Microsoft Knowledge Base [compatibilidad de Microsoft BizTalk Server en una máquina virtual](https://support.microsoft.com/kb/842301). Sin embargo, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] no funcionen según lo esperado si se instala en un sistema operativo compatible que se ejecuta en un software de virtualización distinto de los mencionados en el artículo KB.  
  
## <a name="development-environment"></a>Entorno de desarrollo  
 Los proyectos de BizTalk que se usan para la solución de BizTalk se crean en el entorno de desarrollo. Debe instalar el software siguiente en los equipos utilizados en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno de desarrollo:  
  
-   Servicios de Internet Information Server (IIS)  
  
-   Visual Studio  
  
-   Herramientas de cliente SQL Server  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](incluidos los componentes siguientes)  
  
    -   Documentación  
  
    -   Herramientas administrativas  
  
    -   SDK y herramientas de programadores  
  
    -   Software adicional  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], si la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] son bases de datos que se hospeda localmente durante el desarrollo.  
  
-   Normalmente los desarrolladores deben tener su propio equipo de desarrollo (físico o virtual) con el software necesario instalado.  
  
> [!NOTE]  
>  Se recomienda que adquiera y usar la suscripción de Visual Studio para entornos de no producción. Suscripciones visuales Studio se ofrecen con un importante descuento desde el costo de una licencia comercial para el mismo software. Vea [suscripciones de Visual Studio](https://visualstudio.com/subscriptions).  
  
## <a name="testing-environment"></a>Entorno de pruebas  
 Pruebas unitarias pueden realizarse en un entorno virtual. Sin embargo, debe llevar a cabo el rendimiento de la realización de pruebas en un entorno físico con el hardware y software que es idéntico al entorno de producción.  
  
 El entorno de pruebas se usa para medir las características de rendimiento como el rendimiento máximo sostenible (MST) y el rendimiento de seguimiento sostenible máximo de la solución de BizTalk. Por lo tanto debe coincidir el entorno de producción físico lo más fielmente posible. Para obtener más información acerca de cómo medir el rendimiento se vea las características de una solución de BizTalk [las características de rendimiento del motor](../core/engine-performance-characteristics.md), o la [Guía de optimización de rendimiento de BizTalk Server](../technical-guides/biztalk-server-2010-performance-optimization-guide.md).
  
## <a name="staging-environment"></a>Entorno de ensayo  
 Normalmente se utiliza el entorno de ensayo a "prueba unitaria" la implementación real de la solución de BizTalk. El software instalado en el entorno de ensayo debe coinciden estrechamente con el software instalado en el entorno de producción. Sin embargo, podría ser aceptable utilizar equipos virtuales en el entorno de ensayo, puesto que este entorno no es debe ser usado para medir el rendimiento. Para obtener más información acerca de cómo implementar una aplicación de BizTalk en un entorno de ensayo vea [tareas de almacenamiento provisional para la implementación de aplicación de BizTalk](../core/staging-tasks-for-biztalk-application-deployment.md).
  
## <a name="production-environment"></a>Entorno de producción  
 El entorno de producción es el entorno de "activo" que se va a hospedar la solución de BizTalk en ejecución. El entorno de producción es el extremo final en el proceso de administración de versiones y debe solo aplicaciones de BizTalk de host que hayan sido previamente desarrollo, pruebas unitarias, pruebas de carga y almacenamiento provisional en los otros entornos. Unidad exhaustiva pruebas, las pruebas de carga y almacenamiento provisional will con antelación ayudará a garantizar el máximo rendimiento y tiempo de actividad de la aplicación de BizTalk en el entorno de producción.  
  
## <a name="guidelines-for-allocating-servers"></a>Directrices para la asignación de servidores  
 Las instrucciones siguientes proporcionan una regla general para el número de servidores de BizTalk y SQL Server, debe asignar a cada fase del proceso de administración de versión con un número determinado de equipos físicos de espera para su uso en producción: son aproximadas estimaciones que están sujetos a cambios dependiendo de la arquitectura.  
  
> [!NOTE]  
>  Servidores virtuales pueden utilizarse en el desarrollo y en el entorno de ensayo y también pueden utilizarse para las pruebas unitarias. Todas las pruebas de rendimiento deben realizarse en el hardware físico que coincida con el hardware físico en el entorno de producción.  
  
|Equipos que ejecutan BizTalk Server utilizará en producción (se recomienda un hardware físico)|Servidores de desarrollo (hardware físico o virtual)|Servidores de prueba (se recomienda un hardware físico)|Servidores de ensayo (hardware físico o virtual)|Nº total. de equipos que ejecutan BizTalk Server|  
|---|---|---|---|---|  
|1|2|1|1|5|  
|2|2|2|1|7|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
|No estimado. de equipos que ejecutan SQL Server usada en producción (se recomienda un hardware físico)|Servidores de desarrollo (hardware físico o virtual)|Servidores de prueba (se recomienda un hardware físico)|Servidores de ensayo (hardware físico o virtual)|Nº total. de equipos que ejecutan SQL Server|  
|---|---|---|---|---|  
|1|1|1|1|4|  
|2|1|2|1|6|  
|3|2|3|1|9|  
|4|2|4|1|11|  
  
## <a name="see-also"></a>Vea también  
 [Planear el entorno de BizTalk Server](../technical-guides/planning-the-environment-for-biztalk-server.md)