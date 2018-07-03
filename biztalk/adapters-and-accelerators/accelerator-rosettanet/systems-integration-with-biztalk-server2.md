---
title: Integración de sistemas con BizTalk Server | Microsoft Docs
description: BizTalk Server incluye la capacidad de integrar mensajes mediante XML, automatizar los procesos de negocio mediante mapas y orquestación y trabajar con sistemas mediante protocolos diferentes, como FTP, HTTP, SMTP, SOAP y SQL.
ms.custom: ''
ms.date: 06/08/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ba3dda1-efdb-4a2b-bb3a-825d76696f15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85dd0ce3143373428a810a4e24b3c8b4f679cc14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969421"
---
# <a name="systems-integration-with-biztalk-server"></a>Integración de sistemas con BizTalk Server
BizTalk Server es un servidor de integración que usa un [de publicación y suscripción arquitectura](../../core/publish-and-subscribe-architecture.md). Está diseñado para aplicaciones de comercio electrónico que [usar adaptadores](../../core/using-adapters.md) para recibir y enviar mensajes, implementar [procesos empresariales a través de la orquestación](../../core/defining-business-processes.md)e incluyen [administración y seguimiento ](../../core/management-and-tracking-architecture.md) de estas partes diferentes. BizTalk Server también incluye [administración de socios comerciales](../../core/trading-partner-management-using-biztalk-server.md) para mensajería negocio a negocio, [alta disponibilidad](../../core/planning-for-high-availability3.md) para maximizar el tiempo de actividad, una plataforma de desarrollo para [crear los suyos propios componentes](../../core/developing-custom-components.md), una consola de administración para [administrar artefactos](../../core/operational-and-administrative-tasks-in-your-biztalk-environment.md)y de supervisión para administrar la actividad económica [agregaciones, alertas y perfiles](../../core/using-business-activity-monitoring.md). Esta pila de tecnología proporciona una gama de funcionalidad y características para desarrollar, implementar, funcionamiento y mantenimiento de la solución.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Proporciona los siguientes servicios de integración que puede usar junto con Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] integration services, consulte [Acelerador de BizTalk para RosettaNet ](microsoft-biztalk-accelerator-for-rosettanet-documentation.md).
  
## <a name="message-integration"></a>Integración de mensajes  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se integra a distintas entidades (departamentos, socios, proveedores) mediante la automatización de intercambio de mensajes. Utiliza XML como un protocolo de comunicación común. Definición de esquemas XML (XSD) usa para describir y validar los mensajes y transformaciones XSL (XSLT) que transforme los datos de un mensaje a otro.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor integration enruta los mensajes de una ubicación a otra. Ofrece un modelo de publicador y suscriptor que permite un departamento publicar un documento y otra para suscribirse a él. El departamento de suscripción puede suscribirse al mensaje sin el departamento de publicación lo sepa. Esto permite un control eficaz de las organizaciones asociadas, reemplazando las comunicaciones punto a punto con una organización radial flexible.  
  
## <a name="business-process-automation"></a>Automatización de procesos empresariales  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] automatiza y se integra procesos empresariales mediante el uso de un mapa de proceso que se conoce como una orquestación para vincular un conjunto de acciones relacionadas, distintos en un único proceso. Mediante la creación de una orquestación, puede vincular pasos según el intercambio de datos y análisis, como bucles de recepción, envío, decisiones, el mensaje de mensajes y otras operaciones. Con una orquestación, puede crear un proceso empresarial que se ejecutará automáticamente cuando se produce un evento.  
  
 Uso de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede cambiar dinámicamente un proceso basado en reglas de negocios. Esto le ofrece flexibilidad para cambiar las acciones realizadas en un proceso organizado según consideraciones empresariales. Un ejemplo es restringir el proceso de aprobación de pedidos de facturación a los pedidos a través de un umbral determinado.  
  
  
## <a name="integration-of-heterogeneous-systems"></a>Integración de sistemas heterogéneos  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede integrar los sistemas de TI en un entorno heterogéneo en el que los sistemas de transmitan datos en diferentes protocolos de comunicaciones. Lo hace mediante el uso de adaptadores para conectarse a sistemas que utilicen diferentes protocolos. Admite el uso de adaptadores de archivo, FTP, HTTP, SMTP, SOAP y SQL. Puede crear adaptadores personalizados mediante el adaptador de BizTalk Framework. Para obtener más información, consulte [crear adaptadores personalizados](../../core/developing-custom-adapters.md).
  
## <a name="role-based-tools"></a>Herramientas basadas en rol  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] es un entorno de desarrollo y ejecución en el que los desarrolladores, profesionales de TI y los profesionales de negocios colaboran para crear, implementar, operar, mantener y personalizar el sistema. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] cada uno de estos roles proporciona herramientas personalizadas para su uso.  
  
 Para obtener más información, consulte [A Role-Based producto](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md), y [sobre RosettaNet el Acelerador](../../adapters-and-accelerators/accelerator-rosettanet/learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md).
  
## <a name="see-also"></a>Vea también  
 [Cómo resuelve BizTalk Server la necesidad empresarial](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)
