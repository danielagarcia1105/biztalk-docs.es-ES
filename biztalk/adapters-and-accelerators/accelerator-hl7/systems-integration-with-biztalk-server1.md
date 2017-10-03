---
title: "Integración de sistemas con BizTalk Servidor1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system integration
- BizTalk Server, tools
- business processes, automating
- BTAHL7, BizTalk Server
- BizTalk Server
- BizTalk Server, business process automation
- BizTalk Server, messages
- BizTalk Server, system integration
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13eba7a4a799803340d2757bd39c3e5e9844603e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="systems-integration-with-biztalk-server"></a>Integración de sistemas con BizTalk Server
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] es un servidor de integración diseñado para aplicaciones de comercio electrónico. Se basa en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)] plataforma del sistema, incluidos los [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Windows Server 2008, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], y [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]y aprovecha la funcionalidad de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[vs2012](../../includes/vs2012-md.md)]. Esta pila de tecnología proporciona una gama de funcionalidad y características para desarrollar, implementar, el funcionamiento y mantenimiento de la solución.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Proporciona los siguientes servicios de integración que puede usar junto con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]). Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] servicios de integración, vea [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="message-integration"></a>Integración de mensaje  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]integra las distintas entidades (departamentos, socios comerciales, proveedores y así sucesivamente) mediante la automatización de intercambio de mensajes. Lenguaje de marcado Extensible (XML) utiliza como un protocolo de comunicación común. Definición de esquemas XML (XSD) utiliza para describir y validar mensajes y transformaciones XSL (XSLT) para transformar los datos de un mensaje a otro.  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor integration enruta los mensajes de una ubicación a otra. Ofrece un modelo de publicador y suscriptor que permite un departamento publicar un documento y otra para suscribirse a él. El departamento de suscripción puede suscribirse al mensaje sin el departamento de publicación lo sepa. Esto habilita el control eficaz de las organizaciones asociadas, reemplazando las comunicaciones punto a punto por una organización radial flexible.  
  
## <a name="business-process-automation"></a>Automatización de procesos empresariales  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]automatiza e integra procesos empresariales utilizando un mapa de proceso que llama una orquestación para vincular un conjunto de acciones relacionadas, distintos en un único proceso. Mediante la creación de una orquestación, puede vincular pasos basados en el intercambio de datos y análisis, como bucles de recepción, que envía, decisiones, un mensaje de mensajes y otras operaciones. Una orquestación le permite crear un proceso empresarial que se ejecutará automáticamente cuando se produce un evento.  
  
 Usar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede cambiar dinámicamente un proceso basado en reglas de negocios. Esto le da la flexibilidad para cambiar las acciones realizadas en un proceso organizado según las consideraciones de negocios. Un ejemplo es restringir el proceso de aprobación para los pedidos de facturación a los pedidos a través de un umbral determinado.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]También permite incluir acciones humanas orquestaciones automatizadas, a través de servicios de flujo de trabajo de usuarios.  
  
## <a name="integration-of-heterogeneous-systems"></a>Integración de sistemas heterogéneos  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]puede integrar los sistemas de TI en un entorno heterogéneo en el que los sistemas transmitan datos en diferentes protocolos de comunicaciones. Lo hace mediante el uso de adaptadores para conectarse a sistemas que utilicen diferentes protocolos. Admite el uso de adaptadores de archivo, FTP, HTTP, SMTP, SOAP y SQL. Puede crear adaptadores personalizados mediante el adaptador de BizTalk Framework.  
  
## <a name="role-based-tools"></a>Herramientas basada en roles  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]es un entorno de desarrollo y ejecución en el que los desarrolladores y profesionales de TI, los profesionales de negocios colaboran para crear, implementar, operar, mantener y personalizar el sistema. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]cada uno de estos roles proporciona herramientas personalizados para su uso.  
  
 Para obtener más información, consulte [basada en roles de un producto](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md), y [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué Acelerador de BizTalk para HL7 agrega a BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)