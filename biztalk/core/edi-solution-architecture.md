---
title: "Arquitectura de la solución EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42afbb604a8cef1387418e175a39150f0182c607
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-solution-architecture"></a>Arquitectura de solución EDI
El intercambio electrónico de datos (EDI) es uno de los medios más notables a través del cual las entidades de negocio intercambian datos de forma electrónica. El uso de EDI conlleva la sintaxis y los estándares del mensaje (incluidos ANSI X12 y UN/EDIFACT), el protocolo de mensajería y los transportes. A continuación se presentan las características de mensajería EDI:  
  
-   Los protocolos de mensajería EDI comprueban que los datos siempre llegan de la forma esperada y los datos dañados o erróneos se detectan y se generan informes de ellos de manera automática.  
  
-   Los mecanismos EDI suelen especificar los esquemas de agregación de datos (procesamiento por lotes).  
  
-   Los usuarios a menudo personalizan las definiciones del documento EDI mediante la implementación de un subconjunto o implementación específica de una instrucción EDI.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa los mensajes EDI mediante canalizaciones de recepción y de envío específicas para EDI que pueden analizar y serializar mensajes EDI. En esta sección se describe la arquitectura de soluciones EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], incluidos los detalles del procesamiento de recepción y de envío, de la validación de mensajes y generación de informes de estado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Mensajería EDI](../core/edi-messaging.md)  
  
-   [Rol de los acuerdos en el procesamiento de EDI](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [Cómo BizTalk Server recibe mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [Cómo BizTalk Server envía mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [Validación del mensaje EDI](../core/edi-message-validation.md)  
  
-   [Uso de las extensiones de herramientas XML](../core/using-the-xml-tool-extensions.md)