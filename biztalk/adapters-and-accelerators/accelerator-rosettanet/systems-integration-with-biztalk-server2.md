---
title: Integración de sistemas con BizTalk Server | Documentos de Microsoft
description: BizTalk Server incluye la capacidad de integrar mensajes mediante XML, automatizar procesos empresariales mediante mapas y orquestación y trabajar con sistemas que utilizan distintos protocolos, como FTP, HTTP, SMTP, SOAP y SQL.
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
ms.openlocfilehash: 24d2251bf51e59aea919e20b93ff0f7864f3bf31
ms.sourcegitcommit: 7deb2b5a17d740b777a17566d557b25bdd505302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "35290384"
---
# <a name="systems-integration-with-biztalk-server"></a>Integración de sistemas con BizTalk Server
BizTalk Server es un servidor de integración que usa un [publicar y suscribirse arquitectura](../../core/publish-and-subscribe-architecture.md). Está diseñado para aplicaciones de comercio electrónico que [usar adaptadores de](../../core/using-adapters.md) para enviar y recibir mensajes, implementar [procesos empresariales a través de orquestación](../../core/defining-business-processes.md)e incluyen [administración y seguimiento ](../../core/management-and-tracking-architecture.md) de estas partes diferentes. BizTalk Server también incluye [administración de socios comerciales](../../core/trading-partner-management-using-biztalk-server.md) para la mensajería negocio a negocio, [alta disponibilidad](../../core/planning-for-high-availability3.md) para maximizar el tiempo de actividad, una plataforma de desarrollo para [crear sus propios componentes](../../core/developing-custom-components.md), una consola de administración para [administrar los artefactos de](../../core/operational-and-administrative-tasks-in-your-biztalk-environment.md)y para administrar la supervisión de la actividad económica [agregaciones, alertas y perfiles](../../core/using-business-activity-monitoring.md). Esta pila de tecnología proporciona una gama de funcionalidad y características para desarrollar, implementar, el funcionamiento y mantenimiento de la solución.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Proporciona los siguientes servicios de integración que puede usar junto con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] servicios de integración, vea [el Acelerador de BizTalk para RosettaNet ](microsoft-biztalk-accelerator-for-rosettanet-documentation.md).
  
## <a name="message-integration"></a>Integración de mensaje  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] integra las distintas entidades (departamentos, socios comerciales, los proveedores) mediante la automatización de intercambio de mensajes. Usa XML como un protocolo de comunicación común. Definición de esquemas XML (XSD) utiliza para describir y validar mensajes y transformaciones XSL (XSLT) para transformar los datos de un mensaje a otro.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor integration enruta los mensajes de una ubicación a otra. Ofrece un modelo de publicador y suscriptor que permite un departamento publicar un documento y otra para suscribirse a él. El departamento de suscripción puede suscribirse al mensaje sin el departamento de publicación lo sepa. Esto habilita el control eficaz de las organizaciones asociadas, reemplazando las comunicaciones punto a punto por una organización radial flexible.  
  
## <a name="business-process-automation"></a>Automatización de procesos empresariales  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] automatiza e integra procesos empresariales utilizando un mapa de proceso que se conoce como una orquestación para vincular un conjunto de acciones relacionadas, distintos en un único proceso. Mediante la creación de una orquestación, puede vincular pasos basados en el intercambio de datos y análisis, como bucles de recepción, que envía, decisiones, un mensaje de mensajes y otras operaciones. Con una orquestación, puede crear un proceso empresarial que se ejecutará automáticamente cuando se produce un evento.  
  
 Usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede cambiar dinámicamente un proceso basado en reglas de negocios. Esto le da la flexibilidad para cambiar las acciones realizadas en un proceso organizado según las consideraciones de negocios. Un ejemplo es restringir el proceso de aprobación para los pedidos de facturación a los pedidos a través de un umbral determinado.  
  
  
## <a name="integration-of-heterogeneous-systems"></a>Integración de sistemas heterogéneos  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede integrar los sistemas de TI en un entorno heterogéneo en el que los sistemas transmitan datos en diferentes protocolos de comunicaciones. Lo hace mediante el uso de adaptadores para conectarse a sistemas que utilicen diferentes protocolos. Admite el uso de adaptadores de archivo, FTP, HTTP, SMTP, SOAP y SQL. Puede crear adaptadores personalizados mediante el adaptador de BizTalk Framework. Para obtener más información, consulte [crear adaptadores personalizados](../../core/developing-custom-adapters.md).
  
## <a name="role-based-tools"></a>Herramientas basada en roles  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] es un entorno de desarrollo y ejecución en el que los desarrolladores y profesionales de TI, los profesionales de negocios colaboran para crear, implementar, operar, mantener y personalizar el sistema. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] cada uno de estos roles proporciona herramientas personalizados para su uso.  
  
 Para obtener más información, consulte [A Role-Based producto](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md), y [acelerador sobre el RosettaNet](../../adapters-and-accelerators/accelerator-rosettanet/learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md).
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server resuelve la necesidad empresarial](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)
