---
title: "Planeación de la solución de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 337883ce2ca3b7f28def19898930d872928a8ce4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="plan-for-your-biztalk-solution"></a>Plan para la solución de BizTalk
Uno de los objetivos principales de diseño de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consiste en ofrecer la máxima flexibilidad para alojar las situaciones de procesamiento tantos como sea posible. Debido a esta gran flexibilidad, uno de los principales retos para los desarrolladores de una solución de BizTalk es determinar cómo realizar un mejor uso de las características disponibles en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para mejor sus necesidades empresariales. Planear la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede dividirse en distintas fases que se resumen a continuación.  
  
## <a name="scoping-the-solution"></a>Definir el ámbito de la solución  
  
### <a name="performance-considerations"></a>Consideraciones de rendimiento  
 Al definir el ámbito de la solución de BizTalk, tenga en cuenta lo siguiente:  
  
-   ¿Los adaptadores o aceleradores son necesarios?  
  
-   ¿Cuáles son los requisitos para implementar las orquestaciones en la solución?  
  
-   Requisitos de rendimiento de documento: ¿Cuáles son los requisitos de rendimiento máximo sostenible de la solución?  
  
-   ¿Requisitos de latencia: la capacidad de respuesta es la solución necesario para escenarios de petición-respuesta y solicitudes y respuestas?  
  
-   ¿La medida recuperar la solución de períodos de picos de carga de documento?  
  
-   ¿Cuáles son los requisitos de alta disponibilidad de la solución?  
  
-   ¿Cuáles son los requisitos de seguimiento de documentos de la solución?  
  
-   ¿Cuáles son las características de rendimiento de las aplicaciones dependientes, como un servicio Web remoto u otro sistema? Si las aplicaciones dependientes no hacer frente a la carga necesaria, a continuación, el rendimiento general del sistema disminuye en consecuencia.  
  
-   ¿La aplicación de BizTalk se consumen las bases de datos no relacionados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]? ¿Por ejemplo, si la aplicación de BizTalk consume tablas en una base de datos de SQL Server mediante el adaptador de SQL, las tablas de forma eficaz configuradas?  
  
### <a name="hardware-considerations"></a>Consideraciones acerca del hardware  
 Al definir el ámbito de la solución, cree un diagrama de hardware de alto nivel que incluye lo siguiente:  
  
-   Arquitectura del equipo (por ejemplo, x86, x64 e IA64)  
  
-   Requisitos de CPU (por ejemplo, tipo, velocidad, número, núcleos y uso de Hyper-Threading)  
  
-   Requisitos de RAM para cada equipo  
  
-   Almacenamiento en disco local (tipo, tamaño, velocidad)  
  
-   SAN (requisitos de almacenamiento: número de LUN; Tipo de tarjeta de SAN)  
  
-   Tarjetas de red (número de cada equipo, 100 megabits (Mbps) en lugar de 1 Gigabit (1 Gbps).)  
  
-   ¿Cómo se implementará firewalls en la solución?  
  
-   ¿Se puede usar hardware de equilibrio de carga de red?  
  
-   ¿Son los equipos específicos para su agrupación en clústeres?  
  
-   ¿Va a utilizar un entorno virtual que implican Microsoft Hyper-V Server o cualquier otro producto de virtualización?  
  
## <a name="planning-the-solution"></a>Planificación de la solución  
  
### <a name="solution-milestones-timeline"></a>Escala de tiempo de los hitos de solución  
 Crear una programación con hitos para completar los aspectos específicos de la solución de BizTalk. Establecer los hitos específicos, aumentará la probabilidad de que la solución se completó de manera oportuna.  
  
### <a name="non-microsoft-software-considerations"></a>Consideraciones de Software que no sea de Microsoft  
 Tenga en cuenta lo siguiente al software de Microsoft no se utilizarán con la solución:  
  
-   Determinar cómo el software o hardware necesario obtenido.  
  
-   Planear la capacidad y ajuste de tamaño para asegurarse de que el software no sean de Microsoft no es un cuello de botella en la solución.  
  
-   Determinar un plan de acción para la instalación de software de terceros necesarias.  
  
-   Crear un plan de acción para configurar y optimizar el software de terceros necesarias.  
  
## <a name="preparing-for-the-solution"></a>Preparación de la solución  
 Incluir los elementos siguientes en la fase de preparación:  
  
### <a name="detailed-design-of-the-solution-platform"></a>Diseño detallado de la plataforma de soluciones  
 Un diseño de la solución detallada facilita las comunicaciones y evita suposiciones, lo que mejorarán la agilidad y la eficacia de todas las actividades. Debe documentar completamente los siguientes elementos:  
  
-   Las bases de datos de BizTalk Server y cómo se distribuirán en varios equipos.  
  
-   Diseño de Host de BizTalk y las descripciones de cada host y sus instancias.  
  
-   Descripción de cada orquestación.  
  
-   Descripción de cada canalización.  
  
-   Descripción de los componentes personalizados, como ensamblados .NET y componentes COM +.  
  
 **Diagramas de flujo de mensajes**  
  
 Crear diagramas de flujo de mensaje detallado para ayudar a evitar cualquier confusión o false suposiciones con respecto a lo que se supone que se está produciendo mensajes durante el procesamiento. Al crear los diagramas de flujo de mensaje, se deben considerar los siguientes detalles:  
  
-   Describe el ciclo de vida de cada tipo de mensaje desde el momento en que se llega a una ubicación de recepción hasta que se envían todos los mensajes resultantes y se haya completado todo el procesamiento relacionado.  
  
-   Describe cómo cambia el procesamiento de las condiciones de error.  
  
-   Incluir detalles sobre la correlación, las notificaciones de entrega y confirmaciones.  
  
-   Incluir información de requisito de rendimiento con respecto a la latencia y rendimiento.  
  
 **Detalles de Software que no sea de Microsoft**  
  
 Debe estar plenamente documentado todo el software de terceros que se usa como parte del diseño de la solución detallada.  
  
 **Pila detallado del Hardware**  
  
 Basándose en el diagrama de hardware de alto nivel creado anteriormente, la siguiente información de hardware debe estar plenamente documentada:  
  
-   Procesadores  
  
    -   Tipo  
  
    -   Velocidad  
  
    -   Número de núcleos  
  
    -   Hyperthreading  
  
-   Memoria  
  
    -   Amount  
  
    -   Velocidad  
  
    -   Paridad  
  
-   Red  
  
    -   Número de tarjetas de interfaz de red (NIC)  
  
    -   Velocidad de red  
  
-   SAN  
  
    -   Número de tarjetas de SAN en cada equipo  
  
    -   Número de números de unidad lógica (LUN) para cada equipo y el propósito de cada LUN  
  
    -   Velocidad del área de almacenamiento (SAN) tarjetas de red  
  
    -   Detalles de configuración de tarjeta de SAN  
  
    -   Asignación de disco de SAN, formato y particiones  
  
-   Disco  
  
    -   Detalles de disco local de cada equipo  
  
    -   Formato utilizado para discos locales  
  
    -   Detalles de creación de particiones de discos locales  
  
-   Cache  
  
    -   Cantidad de memoria caché L2  
  
    -   Cantidad de caché L3  
  
 **Pila detallado del Software**  
  
 Se debe documentar la siguiente información de software:  
  
-   Arquitectura, ediciones y versiones de sistema operativo específico  
  
-   Características de sistema operativo específico  
  
-   Software específico instalado en cada equipo  
  
-   Controladores específicos  
  
-   Service Packs y otras actualizaciones  
  
-   Valores de configuración para todas las características de software y sistema operativo usa si varían de valores predeterminados  
  
## <a name="building-out-the-environment-for-the-solution"></a>Crear el entorno para la solución  
 Instrucciones detalladas para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los requisitos de software que se encuentran en el [guías de instalación de BizTalk Server](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
  
## <a name="see-also"></a>Vea también  
 [Planificación del nivel de BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)
