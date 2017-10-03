---
title: "Integración de sistemas con BizTalk Server2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system integration
- tools, BizTalk Server
- BizTalk Server, tools
- BizTalk Server, about BizTalk Server
- BizTalk Server, business processes
- messages, BizTalk Server
- BizTalk Server, messages
- BizTalk Server, system integration
- business processes, BizTalk Server
ms.assetid: 5ba3dda1-efdb-4a2b-bb3a-825d76696f15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b93f0f810259708d301ed683af8c10d364e1cca7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="systems-integration-with-biztalk-server"></a>Integración de sistemas con BizTalk Server
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] es un servidor de integración diseñado para aplicaciones de comercio electrónico. Se basa en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)] plataforma del sistema, incluidos los [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]® 2008, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 2008 R2 o 2008 SP1, y [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] SharePoint® Services y aprovecha de la funcionalidad de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Esta pila de tecnología proporciona una gama de funcionalidad y características para desarrollar, implementar, el funcionamiento y mantenimiento de la solución.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Proporciona los siguientes servicios de integración que puede usar junto con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] servicios de integración, vea [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ayuda.  
  
## <a name="message-integration"></a>Integración de mensaje  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]integra las distintas entidades (departamentos, socios comerciales, los proveedores) mediante la automatización de intercambio de mensajes. Usa XML como un protocolo de comunicación común. Definición de esquemas XML (XSD) utiliza para describir y validar mensajes y transformaciones XSL (XSLT) para transformar los datos de un mensaje a otro.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor integration enruta los mensajes de una ubicación a otra. Ofrece un modelo de publicador y suscriptor que permite un departamento publicar un documento y otra para suscribirse a él. El departamento de suscripción puede suscribirse al mensaje sin el departamento de publicación lo sepa. Esto habilita el control eficaz de las organizaciones asociadas, reemplazando las comunicaciones punto a punto por una organización radial flexible.  
  
## <a name="business-process-automation"></a>Automatización de procesos empresariales  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]automatiza e integra procesos empresariales utilizando un mapa de proceso que se conoce como una orquestación para vincular un conjunto de acciones relacionadas, distintos en un único proceso. Mediante la creación de una orquestación, puede vincular pasos basados en el intercambio de datos y análisis, como bucles de recepción, que envía, decisiones, un mensaje de mensajes y otras operaciones. Con una orquestación, puede crear un proceso empresarial que se ejecutará automáticamente cuando se produce un evento.  
  
 Usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede cambiar dinámicamente un proceso basado en reglas de negocios. Esto le da la flexibilidad para cambiar las acciones realizadas en un proceso organizado según las consideraciones de negocios. Un ejemplo es restringir el proceso de aprobación para los pedidos de facturación a los pedidos a través de un umbral determinado.  
  
 Mediante el uso de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede incluir acciones humanas orquestaciones automatizada a través de servicios de flujo de trabajo de usuarios. Para obtener más información, vea "servicios de flujo de trabajo de usuarios (HWS)" en [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ayuda.  
  
## <a name="integration-of-heterogeneous-systems"></a>Integración de sistemas heterogéneos  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]puede integrar los sistemas de TI en un entorno heterogéneo en el que los sistemas transmitan datos en diferentes protocolos de comunicaciones. Lo hace mediante el uso de adaptadores para conectarse a sistemas que utilicen diferentes protocolos. Admite el uso de adaptadores de archivo, FTP, HTTP, SMTP, SOAP y SQL. Puede crear adaptadores personalizados mediante el adaptador de BizTalk Framework. Para obtener más información, vea "Desarrollar adaptadores utilizando el marco de trabajo" en [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ayuda.  
  
## <a name="role-based-tools"></a>Herramientas basada en roles  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]es un entorno de desarrollo y ejecución en el que los desarrolladores y profesionales de TI, los profesionales de negocios colaboran para crear, implementar, operar, mantener y personalizar el sistema. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]cada uno de estos roles proporciona herramientas personalizados para su uso.  
  
 Para obtener más información, consulte [A Role-Based producto &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md), y [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server resuelve la necesidad empresarial](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)