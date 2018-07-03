---
title: Tiempo de ejecución, reparación, respuesta FIN y mensajería de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 360a2e3974f1e4ea5858c583c5dc5fcc364e9756
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974637"
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a>En tiempo de ejecución, reparación de mensajes, respuesta FIN y mensajería

## <a name="overview"></a>Información general
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona a los clientes y socios con financieros del sector-funcionalidad específica de conectividad y mensajería, lo que ayuda a acelerar la implementación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como middleware para que las organizaciones financieras.  
  
 Mediante el aprovechamiento de los estándares abiertos en la función de las herramientas y las funciones de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para implementar la compatibilidad con formatos de mensaje como SWIFT, A4SWIFT reduce la barrera para la adopción de estándares SWIFT actualizados mediante el empleo del [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] como un uso general plataforma de middleware de integración.  
  
 A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reducir el tiempo de comercialización mientras también reduce el costo total de propiedad (TCO) al reducir el costo general de mantenimiento y soporte técnico de la entrega de servidores de clases para el hospedaje de aplicaciones y la integración, así como flujo de trabajo de enterprise implementación de la industria de servicios financieros.  
  
 Puede categorizar A4SWIFT funcionalidad como la mensajería de SWIFT y conectividad SWIFT. Mensajería de A4SWIFT completa abarca mensaje SWIFT análisis y validación (incluido el procesamiento por lotes entrante y saliente), reparación y entrada de mensaje (incluida la integración con Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] como la herramienta de usuario de front-end) y otros aplicaciones de línea de negocio (LOB).  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] proporciona esquemas XSD y validación completa, incluidas las reglas de red para 358 todos los mensajes (FIN) financieros. También proporciona la desagrupación entrante.  

## <a name="next-steps"></a>Pasos siguientes  
 Esta sección contiene:  
  
-   [Components](components.md)  
  
-   [Acelerador de BizTalk para el tiempo de ejecución de SWIFT](biztalk-accelerator-for-swift-runtime.md)  
  
-   [Reparación de mensajes y Nuevo envío](message-repair-and-new-submission.md)  
  
-   [Conciliación de respuestas de FIN](fin-response-reconciliation.md)  
  
-   [Mensajes de SWIFT](swift-messages.md)

- [Propiedades promocionadas A4SWIFT_*](a4swift-promoted-properties.md)