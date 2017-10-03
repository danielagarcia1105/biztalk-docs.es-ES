---
title: Empezar a trabajar con el Acelerador de BizTalk para HL7 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.gettingstarted
helpviewer_keywords:
- BizTalk Accelerator for HL7
- BizTalk Accelerator for HL7, getting started
- getting started
ms.assetid: e842d501-2037-4fd6-a518-d29b25877250
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bebe61b152c7a74c2d45c0604e23b0a39bc6a4fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a>Empezar a trabajar con el Acelerador de BizTalk para HL7
Mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)], puede desarrollar procesos empresariales entre los sistemas informáticos de atención médica. Mediante el uso de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], los desarrolladores y profesionales de TI, los analistas de interfaz pueden trabajar en un entorno común para desarrollar soluciones de BTAHL7-based de-to-end integradas en todas las aplicaciones de atención médica.  
  
 Más concretamente, con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] puede:  
  
-   **Simplificar la integración de aplicaciones de atención sanitaria**. Crear, administrar y realizar un seguimiento de los procesos empresariales distribuidas mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] entorno de desarrollo.  
  
-   **Normalizar datos clínicos intercambio entre las aplicaciones médicas**. Transformación de transmisión de datos existente entre las aplicaciones la [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] estándar.  
  
-   **Aumentar la eficacia**. Automatizar todos los procesos de comunicación entre las aplicaciones médicas con una intervención manual mínima.  

Esta sección proporciona información específica de un rol acerca de cómo puede usar [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] para facilitar la integración de aplicaciones empresariales (EAI) en hospitales y el ámbito de servicios de salud para automatizar soluciones de asistencia sanitaria de negocio a negocio .  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]proporciona cuatro escenarios independientes en formato tutorial para cada tipo de solución. Antes de comenzar estos tutoriales, debe comprender los conceptos fundamentales en [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]y las herramientas y procesos necesarios para comenzar a crear soluciones con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].  

> [!TIP] 
> Antes de comenzar estas lecciones, [obtener información sobre el Acelerador para HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).  
  
 Las siguientes descripciones proporcionan una visión general de cada [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] tutorial.  
  
## <a name="end-to-end-tutorial"></a>Tutorial de extremo a extremo  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] -to-End tutorial proporcionan con los pasos detallados para facilitar procesos empresariales en un escenario de suscriptor y el publicador. Este escenario es una situación en la que un publicador, por ejemplo, una descarga de admisión y transferencia de sistema envía un mensaje a suscriptores específicos.  
  
 El mensaje se enruta hacia el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] motor de interfaz, que a su vez recibe, procesos, valida, vuelve a dar formato y, a continuación, enruta el mensaje a los suscriptores. Los suscriptores en este escenario son un Hospital información y un sistema de farmacia.  
  
 Este escenario utiliza tipos de adaptador de archivo y el protocolo de nivel inferior mínimo (MLLP). No es necesario tener en cuenta los suscriptores, el publicador y el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] motor interfaz envía una confirmación adecuada en el publicador después de procesar el mensaje.  
  
## <a name="interrogative-tutorial"></a>Tutorial interrogative  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative tutorial proporciona instrucciones detalladas para implementar un sistema de respuesta de la consulta entre subsistemas dentro de una organización. En este escenario, una aplicación de línea de negocio (LOB) en la admisión de descarga y transferir sistema envía una consulta para el sistema de información de salud para obtener resultados de laboratorio paciente. Una vez que el sistema de información de salud recibe la consulta, envía los datos solicitados al sistema que ha emitido la consulta.  
  
 Este escenario usa MLLP como el protocolo de transporte para todos los mensajes, incluidas las confirmaciones.  
  
## <a name="message-enrichment-tutorial"></a>Tutorial de enriquecimiento de mensajes  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] enriquecimiento tutorial proporcionan con los pasos detallados para solucionar un problema empresarial determinado: el escenario de enriquecimiento del mensaje. El escenario de enriquecimiento del mensaje es una situación en la que se deben agregar a, o enriquecer, un mensaje que no es compatible con HL7 o está incompleta. Esta situación puede producirse con una aplicación, como una aplicación de registro paciente, o cuando se va a llenar con datos XML de un mensaje de [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].  
  
 En el escenario de enriquecimiento del mensaje, capturar los mensajes con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]y proporcionar los datos que faltan, por ejemplo, desde una base de datos de registros de paciente. A continuación, convertir el mensaje y enviarlo a un laboratorio, seguro o cualquier aplicación heredado línea de negocio (LOB) con el adaptador MLLP.  
  
## <a name="batching-tutorial"></a>Tutorial de procesamiento por lotes  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] tutorial de procesamiento por lotes proporcionan con los pasos detallados para enviar y recibir mensajes por lotes. Procesamiento por lotes implica la recepción y/o el envío de un grupo de mensajes individuales (o confirmaciones) como un solo mensaje compuesto.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]admite los escenarios de procesamiento por lotes del mensaje tres siguientes:  
  
-   **Fragmentados por lotes entrantes**. En este escenario, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] recibe un lote de mensajes HL7 y, a continuación, enruta los mensajes individuales en el sistema de destino.  
  
-   **Procesar por lotes en / lote**. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.  
  
-   **Crear lote (o procesamiento por lotes saliente)**. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]recibe los mensajes individuales y los lotes antes de enrutarlos al sistema de destino.  
  
## <a name="tutorial-links"></a>Vínculos de tutorial  
  
-   [Tutorial de extremo a extremo](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [Tutorial interrogative](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a>Vea también
  
[Accesibilidad para personas con discapacidades](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)