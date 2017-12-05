---
title: "Guía de Hyper-V de BizTalk Server 2010 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c38ecdd-de72-41d9-b639-2aa6bbfee917
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 937fcb3618bf3bde4883242d48da2a841f00dea5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-server-2010-hyper-v-guide"></a>Guía de Hyper-V de BizTalk Server 2010
El propósito de esta guía es proporcionar una guía práctica para usar Microsoft BizTalk Server con Microsoft [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Hyper-V. El énfasis se encuentra en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], pero los métodos de evaluación de rendimiento y escenarios de pruebas de rendimiento son útiles para analizar el rendimiento de aplicaciones de servidor virtualizado en general. Esta guía será de interés para las Comunidades de profesionales de TI y desarrolladores.  
  
 Para descargar una copia de esta guía, vaya a [http://go.microsoft.com/fwlink/?LinkId=149267](http://go.microsoft.com/fwlink/?LinkId=149267).  
  
## <a name="introduction"></a>Introducción  
 Virtualización de servidores ofrece a las empresas la oportunidad de ejecutar varios sistemas operativos en un solo equipo físico. Esto permite la consolidación de servidores infrautilizados en un menor número de máquinas utilizándose en su totalidad. Mediante la implementación de virtualización, las empresas pueden minimizar operativa y los costos de gastos de capital asociados con la implementación y el funcionamiento de los servidores necesarios para las aplicaciones empresariales.  
  
 El ahorro de costos posibles ha hecho que los departamentos de TI para evaluar las aplicaciones nuevas y existentes para identificar los candidatos adecuados para la virtualización de servidor. Más esas evaluaciones de búsqueda detectar el costo total de la virtualización. El costo total de la virtualización es la suma de monetarios costos de hardware y las operaciones de TI y el costo de rendimiento de virtualización en comparación con el rendimiento alcanzables en un entorno físico. Esta guía se centra exclusivamente en el aspecto del rendimiento de la virtualización.  
  
 A partir de Windows Server 2008, virtualización de servidores mediante la tecnología Hyper-V ha sido una parte integral del sistema operativo. [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]Hyper-V ofrece una solución de virtualización confiable y optimizado que permite a las organizaciones a mejorar la utilización del servidor y reducir los costos. Con la adición de nuevas características como la funcionalidad de migración en vivo, expandida procesador y memoria para los sistemas de host, compatibilidad con el almacenamiento dinámico en máquina virtual, que permite a las organizaciones consolidar cargas de trabajo en un mismo servidor físico y es un buena solución para organizaciones que son la consolidación de servidores, así como para entornos de desarrollo y prueba.  
  
 BizTalk Server aprovecha las ventajas de las mejoras más recientes de virtualización que forma parte de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Hyper-V, lo que puede provocar reduce los costos mediante la consolidación de servidores de producción y administración de la continuidad de negocio, además de la creación de más dinámico Infraestructura de TI. La capacidad de agrupación en clústeres permite que BizTalk Server para implementarse en entornos de agrupación en clústeres de varios sitios sin hardware o software adicional. Hyper-V proporciona compatibilidad para ejecutar varias instancias del servidor BizTalk Server en instancias virtualizadas de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Virtualización de servidores permite a los clientes de BizTalk minimizar el consumo de hardware de una implementación de BizTalk mediante la consolidación de recursos desperdiciados en forma segura.  
  
 Normalmente, una implementación de BizTalk Server consta de un número de otros componentes, como: SQL Server, Windows Server y servicios de Internet Information Server (IIS). Hyper-V proporciona compatibilidad para el aprovisionamiento dinámico a través de System Center Virtual Machine Manager (VMM) que hace que un escenario realista de aprovisionamiento a petición.  
  
 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]proporciona la tecnología Hyper-V para dar cabida a la consolidación de servidores a través de virtualización de varias instancias del sistema operativo en un único servidor físico. Hyper-V se proporciona como una parte fundamental de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] o como un producto independiente para que sea lo más sencillo posible para que los clientes adoptar la virtualización en su organización. Hay varios escenarios claves para la implementación de Hyper-V:  
  
-   **Consolidación de servidores** : minimizar el espacio del servidor, operativa y gastos de capital (TCO) asociados a las aplicaciones en ejecución mediante la consolidación de varios servidores físicos en un solo cuadro.  
  
-   **Pruebas y desarrollo** – usando máquinas virtuales, los arquitectos y desarrolladores pueden aprovisionar rápidamente nuevas máquinas para probar los escenarios en un entorno seguro que refleja con exactitud las características de un entorno físico y la nueva tecnología. La virtualización permite nuevas máquinas se aprovisione ejecuta en una plataforma amplia de sistemas operativos sin que se requiere nuevo hardware. Esto proporciona una plataforma excelente para entornos de desarrollo y pruebas.  
  
-   **Continuidad del negocio y recuperación ante desastres** : Hyper-V incluye continuidad del negocio eficaces y características de recuperación ante desastres como live migración rápida y copia de seguridad que permite a las empresas a satisfacer sus acuerdos de nivel de servicio.  
  
    > [!NOTE]  
    >  Para obtener información sobre cómo realizar copias de seguridad máquinas virtuales de Hyper-V mediante copia de seguridad de Windows Server, consulte Microsoft Knowledge Base el artículo 958662, "cómo hacer copia de seguridad de máquinas virtuales de Hyper-V desde la partición primaria en un equipo de Windows Server 2008 mediante Windows Copia de seguridad de servidor"en [http://go.microsoft.com/fwlink/?LinkId=131207](http://go.microsoft.com/fwlink/?LinkId=131207).  
    >   
    >  Para obtener información sobre cómo usar la característica Hyper-V Live migración disponibles en Windows Server 2008 R2, consulte "Hyper-V: paso a paso Guía para usar Live migración de Windows Server 2008 R2" en [http://go.microsoft.com/fwlink/?LinkID=139667](http://go.microsoft.com/fwlink/?LinkID=139667).  
  
-   **Centro de datos dinámico** : mediante la combinación de Hyper-V con el conjunto de herramientas de Microsoft System Center, las organizaciones pueden automatizar la configuración de máquina virtual y la supervisión. Para obtener más información, consulte "System Center Virtual Machine Manager" en [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303).  
  
 La información de esta guía se relaciona directamente con los escenarios de desarrollo y pruebas y consolidación de servidores de Hyper-V. Los otros dos estaban fuera del ámbito de esta guía.  
  
 Para obtener más información sobre los escenarios principales para Hyper-V, consulte [virtualización con Hyper-V: Introducción](http://go.microsoft.com/fwlink/?LinkID=202438) y los temas de la [Appendices1](../technical-guides/appendices1.md) sección de esta guía.  
  
### <a name="who-should-read-this"></a>¿A quiénes va destinada esta?  
  
-   Todos los profesionales de TI que trabajan con[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Profesionales de TI que implementación, optimizan y mantienen un entorno de aplicación  
  
-   Profesionales de TI que trabajan con los equipos de desarrollo para evaluar y optimizar las arquitecturas de sistema  
  
-   Los desarrolladores que crean y mantienen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones  
  
-   Desarrolladores interesados en la optimización del rendimiento e identificar los cuellos de botella de rendimiento  
  
### <a name="goals-of-this-guide"></a>Objetivo de esta guía  
 El objetivo principal de esta guía es proporcionar instrucciones sobre cómo determinar si BizTalk Server que se ejecutan en Hyper-V es probable que cumpla las expectativas de rendimiento. Esta guía también será de valor como una ayuda para la optimización de un implementado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación.  
  
 Este proyecto se realiza con los siguientes objetivos:  
  
-   Proporcionar instrucciones específicas para cualquier persona que evaluar, diseñar o implementar un virtualizado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
-   Proporciona una introducción a los contadores del monitor de rendimiento y herramientas que se usan para medir las capacidades de rendimiento de una plataforma de servidor virtualizado.  
  
-   Proporcionar directrices para determinar el costo de la virtualización como una función de la diferencia de rendimiento entre los entornos de servidores físicos y virtualizados.  
  
-   Desarrollar prácticas recomendadas para su uso cuando se planea u optimizar un virtualizado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
-   Proporcionar una guía de arquitectura para ayudarle a determinar cómo implementar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtualizado.  
  
-   Identificar y documentar los cuellos de botella de rendimiento en un entorno virtualizado.  
  
### <a name="whats-in-this-guide"></a>¿Qué incluye esta guía?  
 Las instrucciones para implementar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución en un entorno virtualizado de Hyper-V. Esta guía incluye:  
  
-   **Implementación de BizTalk Server en Hyper-V**: [implementación de BizTalk Server en Hyper-V](../technical-guides/deploying-biztalk-server-on-hyper-v.md) describe los pasos que se siguen para configurar el entorno de laboratorio que se utiliza para comparar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución se ejecuta en Máquina virtual de Hyper-V en el mismo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución se ejecuta en hardware físico.  
  
-   **Evaluar el rendimiento del servidor de BizTalk en Hyper-V**: [evaluar el rendimiento del servidor de BizTalk en Hyper-V](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md) detalles consideraciones importantes al medir el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que se ejecuta en un Hyper-V entorno virtualizado.  
  
-   **Probar el rendimiento del servidor de BizTalk en Hyper-V**: [probar el rendimiento de virtualización de BizTalk Server](../technical-guides/testing-biztalk-server-virtualization-performance.md) proporciona resultados detallados de cuatro escenarios distintos de pruebas que comparan el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que se ejecuta en la máquina virtual de Hyper-V en el mismo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución se ejecuta en hardware físico.  
  
-   **Apéndices**: en los temas de [Appendices1](../technical-guides/appendices1.md) proporcionar material de referencia importante de esta guía incluidos:  
  
    -   [Apéndice A: optimizaciones se aplica a equipos en el entorno de prueba](../technical-guides/appendix-a-optimizations-applied-to-computers-in-test-environment.md) : proporciona información detallada acerca de las optimizaciones de rendimiento que se aplicaron a los equipos del entorno de prueba.  
  
    -   [Introducción a las características y arquitectura de Hyper-V de apéndice B:](../technical-guides/appendix-b-hyper-v-architecture-and-feature-overview.md) : proporciona una visión general de arquitectura de Hyper-V, se describen las ventajas y desventajas de Hyper-V y describe las diferencias entre Hyper-V y Virtual Server 2005  
  
    -   [Apéndice C: compatibilidad de Hyper-V de SQL Server y BizTalk Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md) : describe las directivas de soporte técnico para ejecutar BizTalk Server y SQL Server en una máquina virtual de Hyper-V.  
  
    -   [Apéndice D: herramientas para medir el rendimiento](../technical-guides/appendix-d-tools-for-measuring-performance.md) -describe varias herramientas que pueden utilizar para supervisar y evaluar el rendimiento de un entorno de BizTalk Server.  
  
-   **Glosario de**: el [Glossary8](../technical-guides/glossary8.md) define términos clave usados a lo largo de esta guía.