---
title: Guía de optimización de rendimiento de BizTalk Server 2010 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a56b27f-3e57-47db-a776-520f2d67d65e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a16d47f88be211b376f54d0f7116346771d136
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010733"
---
# <a name="biztalk-server-2010-performance-optimization-guide"></a>Guía de optimización de rendimiento de BizTalk Server 2010
Bienvenido a la Guía de optimización de Microsoft® BizTalk® Server 2010 rendimiento. Hemos creado esta guía para proporcionar información detallada para optimizar el rendimiento de una solución de BizTalk Server. Pruebas de rendimiento de end-to-end se suelen pasarse por alto durante la implementación de aplicaciones empresariales. Saber que Microsoft ha creado una infraestructura de mensajería escalable, muchas organizaciones que usan el servidor BizTalk Server dedican tiempo a poca o ninguna realizar pruebas de rendimiento de sus propias aplicaciones. Aplicaciones de BizTalk Server constan de varios elementos, que pueden incluir los componentes, así como los proporcionados por Microsoft. No es posible para todas las combinaciones posibles de estos componentes de prueba de Microsoft para el rendimiento. Por lo tanto, completa y correctamente llevando a cabo una prueba de rendimiento de la aplicación es un paso crítico de cualquier implementación.  
  
 El propósito de esta guía es consolidar y proporcionar instrucciones preceptivas sobre las prácticas recomendadas y técnicas que se deben seguir para optimizar el rendimiento de BizTalk Server.  
  
 Para descargar una copia de esta guía en forma de chm, pdf o docx, vaya a [Guía de optimización de rendimiento de Microsoft BizTalk Server 2010](http://go.microsoft.com/fwlink/?LinkId=210870)(http://go.microsoft.com/fwlink/?LinkId=210870).  
  
## <a name="whats-in-it"></a>¿Qué es lo?  
 Por lo general, el rendimiento de un servidor está determinado por el componente que tiene el rendimiento más bajo, el cuello de botella en el sistema. La clave para mejorar el rendimiento es ser capaz de identificar cuellos de botella, determinar su causa y aplicar la acción correctiva apropiada.  
  
 Cuando planee la implementación de BizTalk Server, use esta guía para ayudar a diseñar y optimizar su entorno. El concepto de rendimiento está estrechamente relacionado con el concepto de escalabilidad. Cuando tenga un conocimiento sólido de los factores que influyen en el rendimiento de componentes del sistema, puede implementar componentes de forma que pueda escalar para admitir los períodos de gran demanda.  
  
 Esta guía proporciona instrucciones para optimizar el rendimiento, en función de la experiencia práctica de profesionales de TI que han trabajado extensamente con BizTalk Server. En concreto, esta guía incluye cuatro secciones principales:  
  
-   **Buscar y eliminar los cuellos de botella**: el [buscar y eliminar los cuellos de botella](../technical-guides/finding-and-eliminating-bottlenecks.md) sección describe los distintos tipos de cuellos de botella de rendimiento ya que afectan a las soluciones de BizTalk Server y obtener información sobre cómo resolver los cuellos de botella.  
  
-   **Optimizar el rendimiento de**: el [optimizar el rendimiento de](../technical-guides/optimizing-performance.md) sección proporcionan instrucciones para optimizar el rendimiento de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]rendimiento está estrechamente relacionado con el rendimiento de la plataforma en la que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado. Esta sección proporcionan recomendaciones para optimizar el rendimiento de ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] plataforma.  
  
-   **Ajuste de escala en un entorno de producción de BizTalk Server**: el [ajuste de escala en un entorno de producción de BizTalk Server](../technical-guides/scaling-a-production-biztalk-server-environment.md) sección proporciona resultados detallados de pruebas de rendimiento de BizTalk Server completado por el equipo de producto de BizTalk . Estas pruebas se centra en la escalabilidad y mide el impacto de la adición de equipos de BizTalk Server, el impacto de agregar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox bases de datos y el impacto de la adición de equipos con BizTalk Server y bases de datos de cuadro de mensajes de BizTalk Server a una solución al mismo tiempo.  
  
    -   Al aumentar el número de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo, para estas pruebas solo uno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos se configuró para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas se centraron exclusivamente en el impacto de agregar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
    -   Al aumentar el número de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensaje usan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas se centraron exclusivamente en el impacto de agregar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
    -   Al aumentar el número de ambos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensaje usan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo. Estas pruebas mide el efecto de agregar ambos agregar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de cuadro de mensajes a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo.  
  
-   **Metodología de pruebas de rendimiento de BizTalk Server**: el [metodología de pruebas de rendimiento de BizTalk Server](../technical-guides/biztalk-server-performance-testing-methodology.md) sección proporciona información detallada acerca de cómo probar y optimizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rendimiento. Incluye información acerca de los criterios de rendimiento para centrarse en y las fases fundamentales que deben aplicarse al evaluar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rendimiento.  
  
## <a name="additions-to-this-version-of-the-guide"></a>Adiciones a esta versión de la Guía  
 [Con Visual Studio para facilitar las pruebas automatizadas](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md) – describe el uso de Visual Studio de pruebas de carga para evaluar el rendimiento de una aplicación de BizTalk Server.  
  
## <a name="acknowledgments"></a>Confirmaciones  
 Los miembros de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo de educación del usuario confirmar expresar las contribuciones pendientes de las siguientes personas para proporcionar comentarios técnicos así como una gran cantidad de contenido de la Guía de optimización del rendimiento de BizTalk Server:  
  
 **Autores**  
  
-   TIM Wieman, Microsoft  
  
-   Paolo Salvatori, Microsoft  
  
-   Trace Young, Microsoft  
  
 **Revisores**  
  
-   TIM Wieman, Microsoft  
  
-   Paolo Salvatori, Microsoft