---
title: "HL7 Integración de sistemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7189802ea981bd26b717f09bb3de0e445c9314
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="systems-integration-with-biztalk-server"></a>Integración de sistemas con BizTalk Server
Microsoft BizTalk Server es un servidor de integración diseñado para las aplicaciones de comercio electrónico. Se genera en Windows Server, SQL Server y SharePoint y aprovecha la funcionalidad de Visual Studio. Esta pila de tecnología proporciona una gama de funcionalidad y características para desarrollar, implementar, el funcionamiento y mantenimiento de la solución.  
  
 BizTalk Server proporciona los siguientes servicios de integración que puede usar junto con el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).  
  
## <a name="message-integration"></a>Integración de mensaje  
 BizTalk Server se integra distintas entidades (departamentos, socios comerciales, proveedores y así sucesivamente) mediante la automatización de intercambio de mensajes. Lenguaje de marcado Extensible (XML) utiliza como un protocolo de comunicación común. Definición de esquemas XML (XSD) utiliza para describir y validar mensajes y transformaciones XSL (XSLT) para transformar los datos de un mensaje a otro.  
  
 El motor de integración de BizTalk Server enruta los mensajes de una ubicación a otra. Ofrece un modelo de publicador y suscriptor que permite un departamento publicar un documento y otra para suscribirse a él. El departamento de suscripción puede suscribirse al mensaje sin el departamento de publicación lo sepa. Esto habilita el control eficaz de las organizaciones asociadas, reemplazando las comunicaciones punto a punto por una organización radial flexible.  
  
## <a name="business-process-automation"></a>Automatización de procesos empresariales  
 BizTalk Server automatiza y se integra procesos empresariales utilizando un mapa de proceso que llama una orquestación para vincular un conjunto de acciones relacionadas, distintos en un único proceso. Mediante la creación de una orquestación, puede vincular pasos basados en el intercambio de datos y análisis, como bucles de recepción, que envía, decisiones, un mensaje de mensajes y otras operaciones. Una orquestación le permite crear un proceso empresarial que se ejecutará automáticamente cuando se produce un evento.  
  
 Uso de BizTalk Server, puede cambiar dinámicamente un proceso basado en reglas de negocios. Esto le da la flexibilidad para cambiar las acciones realizadas en un proceso organizado según las consideraciones de negocios. Un ejemplo es restringir el proceso de aprobación para los pedidos de facturación a los pedidos a través de un umbral determinado.  
  
 BizTalk Server también permite incluir acciones humanas orquestaciones automatizadas, a través de servicios de flujo de trabajo de usuarios.  
  
## <a name="integration-of-heterogeneous-systems"></a>Integración de sistemas heterogéneos  
 BizTalk Server puede integrar los sistemas de TI en un entorno heterogéneo en el que los sistemas transmitan datos en diferentes protocolos de comunicaciones. Lo hace mediante el uso de adaptadores para conectarse a sistemas que utilicen diferentes protocolos. Admite el uso de adaptadores de archivo, FTP, HTTP, SMTP, SOAP y SQL. Puede crear adaptadores personalizados mediante el adaptador de BizTalk Framework.  
  
## <a name="role-based-tools"></a>Herramientas basada en roles  
 BizTalk Server es un entorno de desarrollo y ejecución en el que los desarrolladores y profesionales de TI, los profesionales de negocios colaboran para crear, implementar, operar, mantener y personalizar el sistema. BizTalk Server proporciona cada una de estas funciones con herramientas personalizados para su uso.  
  
 Para obtener más información, consulte [basada en roles de un producto](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md).
  
## <a name="see-also"></a>Vea también  
 [Qué agrega el Acelerador de BizTalk para HL7 a BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)