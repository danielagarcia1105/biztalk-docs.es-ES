---
title: Planeación de la solución de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f337efa7b72a40c37a4cc3f42a2bd5d846923dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970957"
---
# <a name="plan-for-your-biztalk-solution"></a>Plan para la solución de BizTalk
Uno de los objetivos principales del diseño de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consiste en proporcionar la máxima flexibilidad para adaptar los escenarios de procesamiento tantos como sea posible. Debido a este gran flexibilidad, uno de los principales desafíos que enfrentan los desarrolladores de una solución de BizTalk consiste en determinar cómo hacer mejor uso de las características disponibles en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para mejor sus necesidades empresariales. Planear la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede dividirse en fases que se resumen a continuación.  
  
## <a name="scoping-the-solution"></a>Definir el ámbito de la solución  
  
### <a name="performance-considerations"></a>Consideraciones de rendimiento  
 Al definir el ámbito de la solución de BizTalk, tenga en cuenta lo siguiente:  
  
- ¿Qué adaptadores o aceleradores son necesarios?  
  
- ¿Cuáles son los requisitos para implementar las orquestaciones en la solución?  
  
- Requisitos de rendimiento de documento: ¿Cuáles son los requisitos de rendimiento máximo sostenible para la solución?  
  
- ¿Requisitos de latencia: cómo responde la solución tiene que ser para escenarios de solicitud-respuesta y de petición-respuesta?  
  
- ¿Grado recupera la solución de períodos de máxima carga de documento?  
  
- ¿Cuáles son los requisitos de alta disponibilidad de la solución?  
  
- ¿Cuáles son los requisitos de seguimiento de documentos de la solución?  
  
- ¿Cuáles son las características de rendimiento de las aplicaciones dependientes, como un servicio Web remoto u otro sistema? Si las aplicaciones dependientes no Manténgase al día de la carga necesarios, a continuación, el rendimiento general del sistema se degradará en consecuencia.  
  
- ¿La aplicación de BizTalk consuma las bases de datos no relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]? ¿Por ejemplo, si la aplicación de BizTalk está consumiendo tablas en una base de datos de SQL Server mediante el adaptador de SQL, las tablas de forma eficaz configuradas?  
  
### <a name="hardware-considerations"></a>Consideraciones acerca del hardware  
 Al definir el ámbito de la solución, cree un diagrama de hardware de alto nivel que incluye lo siguiente:  
  
-   Arquitectura de equipo (por ejemplo, x86, x64 e IA64)  
  
-   Requisitos de CPU (por ejemplo, tipo, velocidad, número, núcleos y uso de Hyper-Threading)  
  
-   Requisitos de RAM para cada equipo  
  
-   Almacenamiento en disco local (tipo, tamaño, velocidad)  
  
-   SAN (requisitos de almacenamiento: número de LUN; Tipo de tarjeta de SAN)  
  
-   Tarjetas de red (número de cada equipo, 100 megabits (Mbps) en lugar de 1 Gigabit (1 Gbps).)  
  
-   ¿Cómo se implementarán los firewalls en la solución?  
  
-   ¿Se usará el equilibrio de carga de red de hardware?  
  
-   ¿Son equipos específicos se agrupará?  
  
-   ¿Va a utilizar un entorno virtual que afectan a Microsoft Hyper-V Server u otros productos de virtualización?  
  
## <a name="planning-the-solution"></a>Planeación de la solución  
  
### <a name="solution-milestones-timeline"></a>Escala de tiempo de los hitos de solución  
 Crear una programación con hitos para completar los aspectos específicos de la solución de BizTalk. Establecer los hitos específicos, aumentará la probabilidad de que será la solución completa de manera oportuna.  
  
### <a name="non-microsoft-software-considerations"></a>Consideraciones de Software que no sea de Microsoft  
 Cuando el software ajeno a Microsoft se usará con la solución, tenga en cuenta lo siguiente:  
  
-   Determinar cómo el software o hardware necesarios se obtienen.  
  
-   Planear la capacidad y ajuste de tamaño para asegurarse de que el software que no son de Microsoft no es un cuello de botella en la solución.  
  
-   Determinar un plan de acción para la instalación requiere software ajeno a Microsoft.  
  
-   Crear un plan de acción para configurar y optimizar el software necesario de que no sean de Microsoft.  
  
## <a name="preparing-for-the-solution"></a>Preparación para la solución  
 Incluir los siguientes elementos en la fase de preparación:  
  
### <a name="detailed-design-of-the-solution-platform"></a>Diseño detallado de la plataforma de soluciones  
 Un diseño de solución detallada facilita las comunicaciones y evita las suposiciones, lo que mejorarán la agilidad y la eficacia de todas las actividades. Debe documentar completamente los siguientes elementos:  
  
- Las bases de datos de BizTalk Server y cómo se distribuirá en varios equipos.  
  
- Diseño de Host de BizTalk y las descripciones de cada host y sus instancias.  
  
- Descripción de cada orquestación.  
  
- Descripción de cada canalización.  
  
- Descripción de los componentes personalizados como ensamblados .NET y componentes COM +.  
  
  **Diagramas de flujo de mensajes**  
  
  Crear diagramas de flujo de mensaje detallado para ayudar a evitar cualquier confusión o false suposiciones con respecto a qué tiene que estar ocurriendo con los mensajes durante el procesamiento. Al crear los diagramas de flujo de mensaje, se deben considerar los siguientes detalles:  
  
- Describe el ciclo de vida de cada tipo de mensaje desde el momento en que llega a una ubicación de recepción hasta que todos los mensajes resultantes se envían y se ha completado todo el procesamiento relacionado.  
  
- Describe cómo cambia el procesamiento de las condiciones de error.  
  
- Incluir detalles sobre la correlación, las notificaciones de entrega y confirmaciones.  
  
- Incluir información de requisitos de rendimiento con respecto a la latencia y rendimiento.  
  
  **Detalles de Software que no sea de Microsoft**  
  
  Se debe documentar completamente todo el software que no son de Microsoft que se usa como parte del diseño de la solución detallada.  
  
  **Pila detallado del Hardware**  
  
  Compilar en el diagrama de hardware de alto nivel creada anteriormente, la siguiente información de hardware debe estar completamente documentada:  
  
- Procesadores  
  
  -   Tipo  
  
  -   Velocidad  
  
  -   Número de núcleos  
  
  -   Hyperthreading  
  
- Memoria  
  
  -   Amount  
  
  -   Velocidad  
  
  -   Paridad  
  
- red  
  
  -   Número de tarjetas de interfaz de red (NIC)  
  
  -   Velocidad de red  
  
- SAN  
  
  -   Número de tarjetas de SAN en cada equipo  
  
  -   Número de números de unidad lógica (LUN) para cada equipo y el propósito de cada LUN.  
  
  -   Velocidad del área de almacenamiento (SAN) tarjetas de red  
  
  -   Detalles de configuración de tarjeta de SAN  
  
  -   Asignación de disco SAN, formato y creación de particiones  
  
- Disco  
  
  -   Detalles del disco local para cada equipo  
  
  -   Formato utilizado para discos locales  
  
  -   Detalles de creación de particiones de discos locales  
  
- Cache  
  
  -   Cantidad de caché L2  
  
  -   Cantidad de caché L3  
  
  **Pila detallado del Software**  
  
  La siguiente información de software se debe documentar:  
  
- Arquitectura, las ediciones y versiones de sistema operativo específico  
  
- Características del sistema operativo específico  
  
- Software específico instalado en cada equipo  
  
- Controladores específicos  
  
- Service Packs y otras actualizaciones  
  
- Valores de configuración para todas las características de software y sistema operativo usa si difieren de los valores predeterminados  
  
## <a name="building-out-the-environment-for-the-solution"></a>Creación de un entorno para la solución  
 Instrucciones detalladas para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y son los requisitos de software en el [guías de instalación de BizTalk Server](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
  
## <a name="see-also"></a>Vea también  
 [Planificación del nivel de BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)
