---
title: AS2 Compatibilidad en BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8ee230e-8f5f-4b51-99e2-0b38acaf5707
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cccb7103a954e292db6ef4579cf950a8ec13e63
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008229"
---
# <a name="as2-support-in-biztalk-server"></a>Compatibilidad con AS2 en BizTalk Server
En este tema se proporciona una breve descripción general de procesamiento de AS2 y cómo BizTalk Serverlo implementa.  
  
## <a name="introduction-to-as2"></a>Introducción a AS2  
 Un transporte común usado para EDI consiste en las redes de valor agregado (VAN). Se trata de redes privadas que proporcionan servicios de valor agregado, como por ejemplo las pistas de auditoría legalmente obligatorias. Sin embargo, las compañías están migrando hacia el intercambio de documentos EDI a través de Internet. De este modo, los costos se reducen al tiempo que aumenta la flexibilidad y la eficacia además de presentar ventajas en términos de redundancia y escalabilidad.  
  
 El modo más habitual para implementar EDI a través de Internet (EDIINT) es mediante AS2 (del inglés Applicability Statement 2 o declaración de aplicabilidad). La especificación AS2 define el intercambio de datos económicos punto a punto seguro basado en MIME. Los mensajes que contienen un sobre con datos MIME se transmiten mediante HTTP a través de TCP/IP.  
  
 AS2 usa la operación HTTP POST para enviar datos EDI, XML u otros datos económicos. AS2 no se restringe al envío de datos EDI. El URI de la solicitud identifica un proceso que se usará para desempaquetar y controlar datos de mensajes. Se devuelve una notificación de disposición de mensaje como confirmación en el cuerpo del mensaje de respuesta HTTP o mediante una nueva operación HTTP POST en una dirección URL para el remitente original.  
  
 Para obtener más información acerca de la mensajería EDI, vea [mensajería AS2](../core/as2-messaging.md).  
  
## <a name="how-as2-is-implemented-in-biztalk-server"></a>Implementar AS2 en BizTalk Server  
 BizTalk Server incluye funcionalidad nativa que proporciona compatibilidad con AS2. No se trata de un complemento del producto, como pueden ser los adaptadores o aceleradores, sino que está integrado en el producto y proporciona la funcionalidad siguiente:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]usa métodos definidos de AS2 para enviar, recibir y comprobar los mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ayuda a garantizar la seguridad de transferencia de datos mediante cifrado, firma y compresión. Para ello, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa claves de cifrado, firmas digitales y certificados.  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite guardar los mensajes AS2 entrantes y salientes en un almacenamiento sin repudio. Se guardan también mensajes AS2 codificados o descodificados y MDN.  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona la capacidad de conservar los nombres de archivo de datos adjuntos como parte del mensaje AS2.  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite comprobar los mensajes entrantes duplicados.  
  
-   Los MDN se pueden devolver de forma sincrónica a través de la misma conexión al tiempo que se confirma el mensaje o de forma asíncrona a través de una conexión diferente.  
  
-   Puede volver a enviar un mensaje AS2 si no se recibe un MDN dentro de un período de tiempo especificado.  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona informes de estado específicos de AS2. que proporcionan información completa sobre el estado de una transmisión AS2, incluidas las confirmaciones correlacionadas con el intercambio.  
  
-   AS2 requiere que se use el adaptador de HTTP en el lado de recepción y en el lado de envío.  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite invalidar el certificado de firma predeterminado para mensajes AS2 mediante la definición de un certificado por acuerdo. Para obtener instrucciones sobre cómo especificar un certificado diferente para una entidad, consulte [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="as2-components-in-biztalk-server"></a>Componentes de AS2 en BizTalk Server  
 Componentes de BizTalk Server utilizados para el transporte AS2 incluyen lo siguiente:  
  
-   La aplicación EDI de BizTalk que contiene artefactos (canalizaciones y esquemas incluidos) que se necesitan para procesar documentos AS2.  
  
    > [!NOTE]
    >  Al configurar la característica de AS2 en BizTalk Server, el programa de configuración crea esta aplicación. Al crear una aplicación que procesará mensajes AS2, deberá agregar una referencia a la aplicación EDI de BizTalk desde su aplicación. Para obtener más información, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
-   La canalización AS2EdiReceive que realiza el procesamiento AS2 y después el procesamiento EDI de un mensaje EDI recibido a través de AS2. Para obtener más información, consulte [componentes de recepción de AS2](../core/as2-receive-components.md).  
  
-   La canalización AS2Receive que realiza el procesamiento AS2 de un mensaje que no pertenece a EDI recibido a través de AS2. Para obtener más información, consulte [componentes de recepción de AS2](../core/as2-receive-components.md).  
  
-   La canalización AS2EdiSend que realiza el procesamiento EDI y después el procesamiento AS2 de un mensaje EDI que se envía a través de AS2. Para obtener más información, consulte [componentes de envío de AS2](../core/as2-send-components.md).  
  
-   La canalización AS2Send que realiza el procesamiento AS2 de un mensaje que no pertenece a EDI que se envía a través de AS2. Para obtener más información, consulte [componentes de envío de AS2](../core/as2-send-components.md).  
  
-   La interfaz de usuario Administración de acuerdos entre socios comerciales (TPM) que permite definir propiedades de procesamiento para socios comerciales comprometidos con el transporte AS2 de documentos. Para obtener más información, consulte [el rol de los acuerdos en el procesamiento de AS2](../core/the-role-of-agreements-in-as2-processing.md) y **EDI y AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
-   La interfaz de usuario de informes de estado que proporciona información completa sobre los intercambios AS2 y las confirmaciones correlacionadas. Para obtener más información, consulte [EDI y los informes de estado de AS2](../core/edi-and-as2-status-reporting.md).  
  
-   Una herramienta de migración (herramienta de migración de entidades) permite migrar datos de entidades que contiene las propiedades de AS2 de BizTalk Server 2006 R2 o BizTalk Server 2009 a BizTalk Server. Para obtener más información, consulte [migrar artefactos de EDI desde una versión anterior de BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).  
  
## <a name="see-also"></a>Vea también  
 [AS2 Arquitectura de la solución](../core/as2-solution-architecture.md)   
 [EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md)   
 [Desarrollo y configuración de soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)