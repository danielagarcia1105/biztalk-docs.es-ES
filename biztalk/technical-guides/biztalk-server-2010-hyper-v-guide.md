---
title: Guía de Hyper-V de BizTalk Server 2010 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c38ecdd-de72-41d9-b639-2aa6bbfee917
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f07cd5f5406475fad3cfc3b9c1d234c5d93cf1eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975093"
---
# <a name="biztalk-server-2010-hyper-v-guide"></a>Guía de Hyper-V de BizTalk Server 2010
El propósito de esta guía es proporcionar una guía práctica para usar Microsoft BizTalk Server con Microsoft [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Hyper-V. El énfasis está puesto en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], pero los métodos de evaluación de rendimiento y escenarios de pruebas de rendimiento son útiles para analizar el rendimiento de aplicaciones de servidor virtualizado en general. Esta guía será de interés para las Comunidades de profesionales de TI y desarrolladores.  

 Para descargar una copia de esta guía, vaya a [ http://go.microsoft.com/fwlink/?LinkId=149267 ](http://go.microsoft.com/fwlink/?LinkId=149267).  

## <a name="introduction"></a>Introducción  
 Virtualización de servidores ofrece a las empresas la oportunidad de ejecutar varios sistemas operativos en un solo equipo físico. Esto permite la consolidación de servidores subutilizados en un menor número de equipos usados por completo. Mediante la implementación de virtualización, las empresas pueden minimizar operativa y los costos de inversión de capital asociado a implementar y operar los servidores necesarios para las aplicaciones empresariales.  

 Los ahorros de costos potenciales ha hecho que los departamentos de TI a evaluar las aplicaciones nuevas y existentes para identificar a candidatos adecuados para virtualización de servidor. Buscan más esas evaluaciones detectar el costo total de la virtualización. El costo total de la virtualización es la suma de los costos monetarios de hardware y las operaciones de TI y el costo de rendimiento de la virtualización en comparación con el rendimiento alcanzables en un entorno físico. Esta guía se centra exclusivamente en los aspectos de rendimiento de la virtualización.  

 A partir de Windows Server 2008, virtualización de servidores mediante la tecnología Hyper-V ha sido una parte integral del sistema operativo. [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Hyper-V proporciona una solución de virtualización confiable y optimizada, permitiendo a las organizaciones a mejorar la utilización del servidor y reducir los costos. Con la adición de nuevas características como la funcionalidad de migración en vivo, procesador expandido y compatibilidad de memoria para los sistemas de host, compatibilidad con el almacenamiento dinámico en máquina virtual, que permite a las organizaciones consolidar cargas de trabajo en un único servidor físico y es un buena solución para organizaciones que va a consolidar servidores, así como para entornos de desarrollo y pruebas.  

 BizTalk Server aprovecha las ventajas de las últimas mejoras de virtualización que forma parte de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] Hyper-V, lo que puede provocar reduce los costos mediante la consolidación de servidores de producción y administración de continuidad empresarial, además de la creación de una más dinámica Infraestructura de TI. La funcionalidad de agrupación en clústeres permite que BizTalk Server para implementarse en entornos de agrupación en clústeres de varios sitios sin hardware o software adicional. Hyper-V proporciona compatibilidad para ejecutar varias instancias del servidor BizTalk Server en instancias virtualizadas de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Virtualización de servidores permite a los clientes de BizTalk minimizar la superficie de hardware de una implementación de BizTalk mediante la consolidación de recursos infrautilizados de forma segura.  

 Implementación de BizTalk Server normalmente consta de un número de otros componentes, como: SQL Server, Windows Server y Internet Information Services (IIS). Hyper-V proporciona compatibilidad para el aprovisionamiento dinámico a través de System Center Virtual Machine Manager (VMM) que hace que sea un escenario realista de aprovisionamiento a petición.  

 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] proporciona la tecnología Hyper-V para dar cabida a la consolidación de servidores mediante la virtualización de varias instancias del sistema operativo en un único servidor físico. Hyper-V se proporciona como una parte fundamental de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] o como un producto independiente que resulte tan fácil como los clientes pueden adoptar la virtualización en su organización. Hay varios escenarios claves para la implementación de Hyper-V:  

- **Consolidación de servidores** : minimizar el impacto de los servidores, operacional y gastos de capital (TCO) asociados con la ejecución de aplicaciones mediante la consolidación de varios servidores físicos en un cuadro.  

- **Pruebas y desarrollo** : uso de máquinas virtuales, los arquitectos y desarrolladores pueden aprovisionar rápidamente nuevos equipos a probar escenarios en un entorno seguro que refleja con exactitud las características de un entorno físico y la nueva tecnología. La virtualización permite nuevos equipos a aprovisionarse que se ejecuta en una amplia plataforma de sistemas operativos sin que se requiere un hardware nuevo. Esto proporciona una plataforma excelente para entornos de desarrollo y pruebas.  

- **Recuperación ante desastres y continuidad del negocio** : Hyper-V incluye la continuidad del negocio eficaces y las características de recuperación ante desastres, como copia de seguridad y rápida la migración en vivo que permite a las empresas a cumplir sus acuerdos de nivel de servicio.  

  > [!NOTE]  
  >  Para obtener información acerca de cómo la copia de seguridad de máquinas virtuales de Hyper-V mediante la copia de seguridad de Windows Server, consulte Microsoft Knowledge Base, artículo 958662, "cómo hacer una copia de seguridad de máquinas virtuales de Hyper-V de la partición primaria en un equipo con Windows Server 2008 mediante el uso de Windows Copia de seguridad de servidor"en [ http://go.microsoft.com/fwlink/?LinkId=131207 ](http://go.microsoft.com/fwlink/?LinkId=131207).  
  >   
  >  Para obtener información sobre cómo usar la característica Hyper-V Live Migration disponibles en Windows Server 2008 R2, consulte "Hyper-V: paso a paso Guía para usar Live Migration en Windows Server 2008 R2" en [ http://go.microsoft.com/fwlink/?LinkID=139667 ](http://go.microsoft.com/fwlink/?LinkID=139667).  

- **Centro de datos dinámico** : mediante la combinación de Hyper-V con el conjunto de herramientas de Microsoft System Center, las organizaciones pueden automatizar la configuración de máquina virtual y la supervisión. Para obtener más información, consulte "System Center Virtual Machine Manager" en [ http://go.microsoft.com/fwlink/?LinkID=111303 ](http://go.microsoft.com/fwlink/?LinkID=111303).  

  La información de esta guía se relaciona directamente con los escenarios de desarrollo y pruebas y consolidación de servidores de Hyper-V. Los otros dos estaban fuera del ámbito de esta guía.  

  Para obtener más información acerca de escenarios básicos para Hyper-V, consulte [virtualización con Hyper-V: Introducción](http://go.microsoft.com/fwlink/?LinkID=202438) y los temas de la [Appendices1](../technical-guides/appendices1.md) sección de esta guía.  

### <a name="who-should-read-this"></a>¿A quiénes va esto?  

- Todos los profesionales de TI que trabajan con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- Profesionales de TI que implementación, optimizan y mantienen un entorno de aplicaciones  

- Profesionales de TI que trabajan con los equipos de desarrollo para evaluar y optimizar las arquitecturas de sistema  

- Los desarrolladores que crean y mantienen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicaciones  

- Desarrolladores interesados en la optimización del rendimiento e identificar los cuellos de botella de rendimiento  

### <a name="goals-of-this-guide"></a>Objetivos de esta guía  
 El objetivo principal de esta guía es ofrecer orientación sobre cómo determinar si BizTalk Server que se ejecutan en Hyper-V es probable que cumpla las expectativas de rendimiento. Esta guía también será de valor como ayuda para la optimización de una implementada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación.  

 Este proyecto se realizó con los siguientes objetivos:  

- Proporcionar instrucciones específicas para cualquier persona que evaluar, diseñar o implementar un virtualizado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  

- Proporcionar una introducción a los contadores del monitor de rendimiento y herramientas que se usan para medir las capacidades de rendimiento de una plataforma de servidor virtualizado.  

- Proporcionar directrices para determinar el costo de la virtualización como una función de la diferencia de rendimiento entre los entornos de servidores físicos y virtualizados.  

- Desarrollar prácticas recomendadas para su uso cuando se planea u optimizar un virtualizado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  

- Proporcionar una guía de arquitectura para ayudarle a determinar cómo implementar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtualizado.  

- Identifique y documente los cuellos de botella de rendimiento en un entorno virtualizado.  

### <a name="whats-in-this-guide"></a>¿Qué es en esta guía?  
 Instrucciones para implementar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución en un entorno virtualizado de Hyper-V. Esta guía incluye:  

- **Implementación de BizTalk Server en Hyper-V**: [implementación de BizTalk Server en Hyper-V](../technical-guides/deploying-biztalk-server-on-hyper-v.md) se describen los pasos seguidos para configurar el entorno de laboratorio que se utiliza para comparar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] soluciones que se ejecutan en Máquina virtual de Hyper-V en el mismo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que se ejecuta en hardware físico.  

- **Evaluar el rendimiento de BizTalk Server en Hyper-V**: [evaluar el rendimiento del servidor de BizTalk en Hyper-V](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md) detalla las consideraciones importantes al medir el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] soluciones que se ejecutan en Hyper-V entorno virtualizado.  

- **Probar el rendimiento de BizTalk Server en Hyper-V**: [probar el rendimiento de BizTalk Server Virtualization](../technical-guides/testing-biztalk-server-virtualization-performance.md) proporciona resultados detallados de cuatro escenarios de prueba distintos que comparan el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que se ejecuta en la máquina virtual de Hyper-V en el mismo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución que se ejecuta en hardware físico.  

- **Apéndices**: en los temas de [Appendices1](../technical-guides/appendices1.md) proporcionar material de referencia importante para esta guía incluidos:  

  -   [Apéndice A: optimizaciones se aplica a los equipos en el entorno de prueba](../technical-guides/appendix-a-optimizations-applied-to-computers-in-test-environment.md) : proporciona información detallada sobre las optimizaciones de rendimiento que se aplicaron a los equipos del entorno de prueba.  

  -   [Introducción a las características y arquitectura de Hyper-V Apéndice B:](../technical-guides/appendix-b-hyper-v-architecture-and-feature-overview.md) : proporciona información general de arquitectura de Hyper-V, describe las ventajas y desventajas de Hyper-V y se describen las diferencias entre Hyper-V y Virtual Server 2005  

  -   [Apéndice C: compatibilidad de Hyper-V de SQL Server y BizTalk Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md) : describe las directivas de soporte técnico para la ejecución de BizTalk Server y SQL Server en una máquina virtual de Hyper-V.  

  -   [Apéndice D: herramientas para medir el rendimiento](../technical-guides/appendix-d-tools-for-measuring-performance.md) -se describen varias herramientas que pueden usarse para supervisar y evaluar el rendimiento de un entorno de BizTalk Server.  

- **Glosario**: el [Glossary8](../technical-guides/glossary8.md) define términos clave usados a lo largo de esta guía.
