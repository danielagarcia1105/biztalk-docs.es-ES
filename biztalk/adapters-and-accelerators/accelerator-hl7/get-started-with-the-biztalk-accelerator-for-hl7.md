---
title: Empezar a trabajar con el Acelerador de BizTalk para HL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.gettingstarted
helpviewer_keywords:
- BizTalk Accelerator for HL7
- BizTalk Accelerator for HL7, getting started
- getting started
ms.assetid: e842d501-2037-4fd6-a518-d29b25877250
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14559d888bc020a5772fbbc6eddf3ba4fdb4beb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989605"
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a>Empezar a trabajar con el Acelerador de BizTalk para HL7
Usar Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)], puede desarrollar procesos empresariales entre los sistemas informáticos de atención médica. Mediante el uso de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], desarrolladores, profesionales de TI y analistas de interfaces que pueden trabajar en un entorno común para desarrollar las soluciones basadas en BTAHL7 integradas de extremo a otro en todas las aplicaciones de atención médica.  
  
 Más específicamente, con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] puede:  
  
- **Simplificar la integración de aplicaciones de atención médica**. Crear, administrar y realizar un seguimiento de procesos empresariales distribuidos con el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] entorno de desarrollo.  
  
- **Estandarizar datos clínicos intercambio entre aplicaciones médicas**. Transformar la transmisión de datos existente entre las aplicaciones, el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] estándar.  
  
- **Aumentar la eficacia**. Automatizar todos los procesos de comunicación entre aplicaciones médicas, con mínima intervención manual.  

Esta sección proporciona información específica de la función acerca de cómo puede usar [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] para facilitar la Enterprise Application Integration (EAI) dentro de hospitales y el sector sanitario para automatizar soluciones de asistencia sanitaria de negocio a negocio .  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] proporciona cuatro escenarios independientes en el formato de tutorial para cada tipo de solución. Antes de comenzar estos tutoriales, debe comprender los conceptos fundamentales en [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]y las herramientas y procesos necesarios para empezar a crear soluciones con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].  

> [!TIP] 
> Antes de comenzar estas lecciones, [Obtenga información sobre el Acelerador de HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).  
  
 Las descripciones siguientes proporcionan una descripción general de cada [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] tutorial.  
  
## <a name="end-to-end-tutorial"></a>Tutorial de extremo a otro  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] -to-End tutorial le ofrece pasos detallados para facilitar procesos empresariales en un escenario de suscriptor y el publicador. Este escenario es una situación en la que un publicador, por ejemplo, una estancia de pacientes y del sistema de transferencia envía un mensaje a suscriptores específicos.  
  
 El mensaje se enruta a la [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] motor de interfaz, que a su vez recibe, procesos, valida, vuelve a dar formato y, a continuación, enruta el mensaje a los suscriptores. Los suscriptores en este escenario son un sistema de información del Hospital y un sistema de farmacia.  
  
 Este escenario utiliza tipos de adaptador de archivo y protocolo de nivel inferior mínimo (MLLP). No debe ser consciente de los suscriptores, el publicador y el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] motor interfaz envía una confirmación correspondiente al publicador después de procesar el mensaje.  
  
## <a name="interrogative-tutorial"></a>Tutorial de interrogación  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] interrogación tutorial proporciona instrucciones detalladas para implementar un sistema de respuesta de la consulta entre subsistemas dentro de una organización. En este escenario, una aplicación de línea de negocio (LOB) en la admisión, descarga y transferir sistema envía una consulta al sistema de información de Hospital para obtener resultados de pacientes de laboratorio. Una vez que el sistema de información de Hospital recibe la consulta, envía los datos solicitados al sistema que ha emitido la consulta.  
  
 Este escenario utiliza MLLP como el protocolo de transporte para todos los mensajes, incluidas las confirmaciones.  
  
## <a name="message-enrichment-tutorial"></a>Tutorial de enriquecimiento de mensajes  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] enriquecimiento tutorial le ofrece los pasos detallados para solucionar un problema empresarial determinado: el escenario de enriquecimiento del mensaje. El escenario de enriquecimiento del mensaje es una situación en la que tendrá que agregar a o enriquecer, un mensaje que no es compatible con HL7 o está incompleta. Esta situación puede producirse con una aplicación, como una aplicación de registro del paciente, o cuando se va a llenar con datos XML de un mensaje de [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].  
  
 En el escenario de enriquecimiento del mensaje, captura los mensajes con [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]y proporcionar los datos que faltan, por ejemplo, desde una base de datos de registros de paciente. A continuación, convertir el mensaje y enviarlo a un laboratorio, seguro o cualquier aplicación heredado línea de negocio (LOB) mediante el adaptador de MLLP.  
  
## <a name="batching-tutorial"></a>Tutorial de procesamiento por lotes  
 El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] tutorial de procesamiento por lotes le ofrece pasos detallados para enviar y recibir mensajes por lotes. Procesamiento por lotes implica la recepción o el envío de un grupo de mensajes individuales (o las confirmaciones) como un solo mensaje compuesto.  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] admite los tres siguientes escenarios procesamiento por lotes de mensajes:  
  
- **Lote de entrada fragmentado**. En este escenario, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] recibe un lote de mensajes de HL7 y, a continuación, enruta los mensajes individuales para el sistema de destino.  
  
- **Procesar por lotes en o salida**. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.  
  
- **Creación de lote (o el procesamiento por lotes saliente)**. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] recibe los mensajes individuales y crea los lotes antes de enrutarlos al sistema de destino.  
  
## <a name="tutorial-links"></a>Vínculos de tutorial  
  
-   [Tutorial integral](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [Tutorial de interrogación](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a>Vea también
  
[Accesibilidad para personas con discapacidades](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)