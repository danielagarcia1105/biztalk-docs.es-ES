---
title: "Fase 4: Crear el entorno de evaluación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8246ccd34d36f42bf9d8013baf8b73d557fae6eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="phase-4-building-the-assessment-environment"></a>Fase 4: Crear el entorno de evaluación
La fase de laboratorio de compilación de una evaluación de rendimiento se usa para instalar el hardware y software para el entorno de acuerdo a las decisiones de diseño adoptadas para fases anteriores. Dado que la fase de laboratorio de compilación puede llevar mucho tiempo, no es inusual para esta fase superponer las fases anteriores. En muchos escenarios, el hardware y el sistema operativo pueden instalarse antes de que se ha tomado una decisión final en cuanto a la arquitectura de la aplicación. Normalmente, la fase de laboratorio de compilación de una evaluación de rendimiento incluye las tareas descritas en este tema.  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a>Obtener todas las infraestructura del laboratorio de compilación al menos una semana antes de la fecha de inicio de laboratorio  
 Debe tener disponible de todos los requisitos de hardware y software al menos una semana antes de la fecha de laboratorio. Así se asegurará de que no pierde tiempo de laboratorio valiosa para desea de la infraestructura necesaria.  
  
## <a name="configure-third-party-software-systems"></a>Configurar los sistemas de software de terceros  
 Puede haber sistemas de terceros que necesitan ser creado y configurado para que pueda comenzar la práctica. Si son necesarios para estos sistemas de expertos en la materia (PYME), asegúrese de que estén programadas durante las fases de ejecución fuera de la compilación y laboratorio. Asegúrese de que documentar minuciosamente sus procedimientos de creación.  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a>Instalar y configurar el entorno de BizTalk Server  
 Instrucciones detalladas para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el software de la dependencia necesaria se encuentra en la [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=191321) (http://go.microsoft.com/fwlink/?LinkID=191321). Después de instalar y configurar el entorno de BizTalk Server correctamente, complete las tareas siguientes:  
  
-   Siga las recomendaciones enumeradas en la [listas de comprobación de preparación operativa](http://go.microsoft.com/fwlink/?LinkId=160134)(http://go.microsoft.com/fwlink/?LinkId=160134).  
  
-   Siga las recomendaciones de [optimizar el rendimiento](../technical-guides/optimizing-performance.md).  
  
-   Asegúrese de que todas las horas del equipo se han sincronizado correctamente.  
  
-   Comprobar la funcionalidad MSDTC entre todos los equipos en el entorno.  
  
-   Asegúrese de que cualquier seguimiento/registro personalizado está deshabilitada a menos que sea absolutamente necesario.  
  
-   Instalar la edición de Visual Studio 2010 Ultimate para pruebas de carga.  Para obtener más información sobre cómo realizar las pruebas automatizadas mediante Visual Studio, vea [con Visual Studio para facilitar las pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md).  
  
-   Configurar los contadores del Monitor de rendimiento y registros, según sea necesario.  
  
-   Configurar un equipo de depuración para depurar la solución si hay cambios en el código dentro del ámbito de la evaluación del rendimiento.  
  
-   Desfragmente todos los discos duros.  
  
-   Deshabilite el examen del antivirus en tiempo real.  
  
-   Hacer copia de seguridad del Enterprise Single Sign-On secreto principal.  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a>Instalar la aplicación de BizTalk Server se va a probar  
 Instalación de la aplicación se va a probar incluirá, normalmente, los pasos siguientes:  
  
1.  Use la consola de administración de BizTalk Server para hacer lo siguiente:  
  
    -   Crear Hosts  
  
    -   Crear controladores de envío y recepción.  
  
    -   Crear instancias de Host.  
  
    -   Crear aplicaciones de BizTalk Server.  
  
2.  Instalación de la aplicación:  
  
    1.  Implementar archivos binarios de BizTalk Server en el grupo de BizTalk Server.  
  
    2.  Importar enlaces en el grupo de BizTalk Server.  
  
    3.  Archivos binarios de GAC BizTalk Server y no de BizTalk Server en todos los cuadros.  
  
    4.  Asegúrese de que existen componentes de dependencia en todos los cuadros.  
  
3.  Instalar aplicaciones de dependencia.  
  
4.  Configurar transportes y los extremos físicos en la consola de administración de BizTalk Server.  
  
5.  Iniciar los servicios.  
  
6.  Realizar pruebas básicas de humos: pruebas de humo son pruebas funcionales-to-end que probar la funcionalidad básica de la solución.  
  
## <a name="implement-automated-build-and-load-testing"></a>Implementar automatizado de compilación y prueba de carga  
 Implementación de una compilación automatizada y el proceso de prueba de carga sin duda es la piedra angular de una evaluación del rendimiento de BizTalk Server. Se debe implementar un proceso automatizado de compilación si hay cambios en el código dentro del ámbito de la evaluación del rendimiento. Pruebas de carga automatizada se deben implementar para todos los escenarios de prueba de carga. La inversión de tiempo inicial necesaria para implementar automatizado de compilación y prueba de carga es recuperar rápidamente, permite la automatización de la repetición rápida y precisa de las tareas rutinarias de compilación y pruebas que están sujetas a errores humanos. Para obtener más información acerca de cómo implementar una compilación automatizada y probar el proceso, consulte [implementar las pruebas automatizadas](../technical-guides/implementing-automated-testing.md) en esta guía.  
  
## <a name="configure-performance-monitoring"></a>Configurar la supervisión de rendimiento  
 Supervisión de rendimiento precisos es fundamental para el éxito de la evaluación del rendimiento. Determinar qué medidas de rendimiento deben evaluarse en función de los objetivos de rendimiento y la latencia que se definieron en la fase de ámbito. Supervisión de rendimiento debe realizarse en cada equipo en el entorno de BizTalk Server. Para obtener más información acerca de los contadores de rendimiento disponibles para BizTalk Server 2010, consulte [contadores de rendimiento](http://go.microsoft.com/fwlink/?LinkID=157269) (http://go.microsoft.com/fwlink/?LinkID=157269) en la Ayuda de BizTalk Server 2010. Utilice la herramienta de análisis de registros de rendimiento (PAL) para generar informes HTML que gráficamente los contadores de rendimiento importantes del gráfico y generan alertas cuando se superan los umbrales de estos contadores. Para obtener más información sobre la [herramienta de análisis de rendimiento de registros (PAL)](http://go.microsoft.com/fwlink/?LinkID=98098), consulte [herramienta de análisis de rendimiento de registros (PAL)](http://go.microsoft.com/fwlink/?LinkID=98098) (http://go.microsoft.com/fwlink/?LinkID=98098).  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a>Establecer y documentar el rendimiento de línea de base de la solución  
 Rendimiento de línea de base se debe calcular para que se puede medir el efecto de las optimizaciones de rendimiento que se aplican durante la evaluación del rendimiento.  
  
## <a name="see-also"></a>Vea también  
 [Fases de una evaluación del rendimiento](../technical-guides/phases-of-a-performance-assessment.md)