---
title: 'Fase 3: Preparar para la evaluación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890047f6a13352d89d33d9514883dc20eacd4001
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301844"
---
# <a name="phase-3-preparing-for-the-assessment"></a>Fase 3: Preparar para la evaluación
Fase de una evaluación de rendimiento puede considerarse el "cómo" para la fase de ámbito "qué" y la fase de planificación de preparación 's "cuando". En este momento en la evaluación del rendimiento, todas las partes interesadas deben acordados por el ámbito de la interacción y los planes para llevar a cabo el laboratorio. Se encuentra en la fase de preparación de la evaluación del rendimiento que se ejecutan los planes y se realizan acciones para preparar para la ejecución del laboratorio de rendimiento.  
  
 En este tema se describe los distintos aspectos de la fase de preparación de una evaluación del rendimiento de BizTalk Server.  
  
## <a name="detailed-design-of-the-solution-platform"></a>Diseño detallado de la plataforma de soluciones  
 Un diseño de la solución detallada facilita las comunicaciones y evita suposiciones, lo que mejorarán la agilidad y la eficacia de todas las actividades. Debe documentar completamente los siguientes elementos:  
  
-   **Bases de datos de BizTalk Server y cómo se distribuirán en varios equipos** -rendimiento de SQL Server es uno de los factores clave en el rendimiento general de BizTalk Server. Si SQL Server tiene las restricciones de recursos, esto afectará a la capacidad de BizTalk Server para procesar los mensajes. El factor principal que influye en el rendimiento de la base de datos de BizTalk es la velocidad de los discos que se hospedan en. Separar los archivos de base de datos y registros de transacciones para cada BizTalk base de datos en unidades independientes o LUN de SAN se ha demostrado que mejorar notablemente el rendimiento general del servidor BizTalk Server. Por lo tanto, es importante que esta información se registra de forma fácilmente accesible. Los valores que se utilizarán en el entorno de producción se deben documentar en el diseño de la solución detallada. En la tabla siguiente proporciona un ejemplo de cómo hacerlo.  
  
    |Base de datos de BizTalk|Nombre del volumen|Archivos|LUN # o ML_ #|Tamaño LUN físico (GB)|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |Cuadro de mensajes|Data_TempDb_1|Archivos de datos TEMPDB, maestra y MSDB|1|134|  
    ||Logs_TempDb_1|Archivos de registro de transacciones de TEMPDB, maestra y MSDB|2|134|  
    ||Data_BtsMsgBox|Archivo de datos de BizTalkMsgBoxDb|3|134|  
    ||Logs_BtsMsgBox|Archivo de registro de transacciones BizTalkMsgBoxDb|4|134|  
    |BAM|Data_TempDb_2|Archivos de datos TEMPDB, maestra y MSDB|5|67|  
    ||Logs_TempDb_2|Archivos de registro de transacciones de TEMPDB, maestra y MSDB|6|67|  
    ||Data_BAM|Archivo de datos BAMPrimaryImport|7|134|  
    ||Logs_BAM|Archivo de registro de transacciones BAMPrimaryImport|8|134|  
    |Bases de datos de seguimiento de BizTalk, administración, Single Sign-On y motor de reglas|Data_TempDb_3|Archivos de datos TEMPDB, maestra, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO y BizTalkRuleEngineDb|9|67|  
    ||Logs_TempDb_3|Archivos de registro de transacciones de TEMPDB, maestra, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO y BizTalkRuleEngineDb|10|67|  
  
-   **Diseño de Host de BizTalk y las descripciones de cada host y sus instancias.**  
  
-   **Descripción de cada orquestación.**  
  
-   **Descripción de cada canalización.**  
  
-   **Descripción de los componentes personalizados, como ensamblados .NET y componentes COM +.**  
  
## <a name="detailed-architecture-diagram"></a>Diagrama de arquitectura detallada  
 El siguiente diagrama muestra un diagrama de arquitectura que podría utilizarse para una evaluación del rendimiento.  
  
 ![Diagrama de arquitectura de BizTalk](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")  
Diagrama de arquitectura de BizTalk  
  
## <a name="message-flow-diagrams"></a>Diagramas de flujo de mensajes  
 Crear diagramas de flujo de mensaje detallado para ayudar a evitar confusiones o false suposiciones sobre lo que se supone que se está produciendo mensajes durante el procesamiento.  
  
 Al pensar en una solución de BizTalk completo, se tiende a pensar en el flujo de mensajes a través del sistema. Esta perspectiva de flujo de mensajes es especialmente importante al realizar pruebas debido a que todas las partes del flujo de deben considerarse como posibles cuellos de botella de rendimiento. Tener un diagrama de flujo de mensaje evita cualquier confusión o ejecutan suposiciones falsas con respecto a lo que se supone que se está produciendo mensajes durante cada prueba.  
  
 En el ejemplo siguiente, creado con formas de Visio simples, todos los usuarios en el proyecto independientemente del fondo pueden comprender rápidamente cómo se obtiene un mensaje en el sistema qué partes de las soluciones de interactuar con el mensaje y, por último, donde el mensaje aterriza después de procesamiento.  
  
 ![Diagrama de flujo de mensajes](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")  
Diagrama de flujo de mensaje  
  
 Al crear los diagramas de flujo de mensaje, se deben considerar los siguientes detalles:  
  
-   Describe el ciclo de vida de cada tipo de mensaje desde el momento en que se llega a una ubicación de recepción hasta que se envían todos los mensajes resultantes y se haya completado todo el procesamiento relacionado.  
  
-   Describe cómo cambia el procesamiento de las condiciones de error.  
  
-   Incluir detalles sobre la correlación, las notificaciones de entrega y confirmaciones.  
  
-   Incluir detalles sobre la dependencia de sistemas externos.  
  
-   Incluir información de requisito de rendimiento con respecto a la latencia y rendimiento.  
  
## <a name="third-party-software-details"></a>Detalles de software de terceros  
 Debe estar plenamente documentado todo el software de terceros que se usa como parte del diseño de la solución detallada.  
  
## <a name="detailed-lab-hardware-stack"></a>Pila de hardware de laboratorio detallada  
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
  
## <a name="detailed-lab-software-stack"></a>Pila de software de laboratorio detallada  
 Se debe documentar la siguiente información de software:  
  
-   Arquitectura, ediciones y versiones de sistema operativo específico  
  
-   Características de sistema operativo específico  
  
-   Software específico instalado en cada equipo  
  
-   Controladores específicos  
  
-   Service Packs y otras actualizaciones  
  
-   Valores de configuración para todas las características de software y sistema operativo usa si varían de valores predeterminados  
  
## <a name="see-also"></a>Vea también  
 [Fases de una evaluación del rendimiento](../technical-guides/phases-of-a-performance-assessment.md)