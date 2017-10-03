---
title: AS2 Procesamiento en BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0027d3db-24a5-459d-9f4e-a75f49d31d82
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11a5bb12d9a7b21a18b92162370d7be14feda8dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-processing-in-biztalk-server"></a>Procesamiento de AS2 en BizTalk Server
En este tema se proporciona una visión general del procesamiento de recepción y de envío de los mensajes AS2 y de cómo los acuerdos entre socios comerciales ayudan a lograr la mensajería AS2.  
  
## <a name="trading-partner-agreements-for-as2-processing"></a>Acuerdos entre socios comerciales para el procesamiento de AS2  
 Los acuerdos entre socios comerciales desempeñan un rol clave en la compatibilidad de AS2 en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La mayoría de las funciones administrativas y de configuración relacionadas con el procesamiento de AS2 en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se realizan mediante la configuración de acuerdos entre socios comerciales para los perfiles de negocio. Los acuerdos unen propiedades comunes de procesamiento de mensaje bidireccionales de perfiles específicos del negocio de ambos socios. Los acuerdos se basan en la configuración de protocolo definida para cada perfil de negocio. Para implementar un acuerdo entre socios comerciales de dos perfiles de negocio, debe definir propiedades para cada perfil de negocio que va a intercambiar mensajes. Establezca propiedades para cada perfil de negocio como receptor de mensaje AS2 y remitente de mensaje AS2 en la interfaz de usuario de administración de socios comerciales (TPM). Las pantallas TPM se encuentran en el **partes** nodo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. No es necesario ser programador para configurar el procesamiento de AS2 en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Puede especificar las propiedades de AS2 como parte de la "configuración de protocolo de transporte" de un perfil de negocio o al especificar directamente la configuración de AS2 en el acuerdo entre socios comerciales. Para obtener más información acerca de la configuración del protocolo, vea [configuración del protocolo](../core/protocol-settings.md). Para obtener más información acerca de los acuerdos, vea [acuerdo de socios comerciales](../core/trading-partner-agreement.md).  Configure la siguiente funcionalidad AS2 mediante la configuración de las propiedades específicas de AS2:  
  
-   Seleccionar las opciones de almacenamiento sin repudio  
  
-   Especificar las propiedades de cifrado, compresión y firma para los mensajes salientes  
  
-   Solicitar MDN para mensajes salientes  
  
-   Establecer propiedades para los MDN entrantes mediante la anulación de las propiedades de MDN, cifrado, compresión y firma en el encabezado del mensaje AS2  
  
 Para obtener más información sobre los acuerdos entre socios comerciales cómo ayudan en el procesamiento de AS2, vea [el rol de los acuerdos en el procesamiento de AS2](../core/the-role-of-agreements-in-as2-processing.md).  
  
> [!NOTE]
>  No existen propiedades globales para el procesamiento de AS2 como las hay para el procesamiento de EDI.  
  
## <a name="as2-receive-side-processing"></a>Procesamiento de recepción de AS2  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje AS2, lo procesa en una canalización de recepción de AS2. Existe una canalización para recibir un mensaje EDI a través de AS2 (AS2EdiReceive), que realiza el procesamiento AS2 y EDI. Otra canalización (AS2Receive) realiza solo procesamiento AS2 para mensajes que no son EDI recibidos a través de AS2.  
  
 El procesamiento de recepción de AS2 incluye lo siguiente:  
  
-   Búsqueda de acuerdos entre socios comerciales  
  
    > [!NOTE]
    >  En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la definición de entidad incluía también la definición del acuerdo. De este modo, cuando la canalización de recepción buscaba las propiedades de la entidad, buscaba internamente la definición del acuerdo dentro de la definición de la entidad y, a continuación, procesaba los mensajes de forma correspondiente. Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puesto que la entidad (o socio comercial) es distinta del acuerdo entre socios comerciales, la canalización de recepción busca específicamente el acuerdo entre socios comerciales.  
  
    > [!NOTE]
    >  Si se deshabilitan todos los acuerdos en los que se resuelve un mensaje, el mensaje se suspenderá.  Además, se registra una advertencia en el registro de eventos.  
  
-   Guardado de copias del mensaje en la base de datos sin repudio  
  
-   Comprobación de mensajes duplicados  
  
-   Procesamiento de mensajes que contienen varios documentos  
  
-   Recuperación un nombre de archivo de documento del sobre MIME  
  
-   Descifrado del mensaje  
  
-   Descompresión del mensaje  
  
-   Comprobación de la firma digital del mensaje  
  
-   Generación de una respuesta HTTP  
  
-   Generación de una respuesta MDN  
  
 Algunas de las consideraciones que debe tener en cuenta al usar el procesamiento del lado de recepción AS2 son las siguientes:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devuelve un MDN en modo sincrónico o asíncrono. Si el MDN se va a devolver de forma asíncrona, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe enviarlo a través de un puerto de envío separado.  
  
-   Cuando recibe un archivo que no sea EDI (no XML) a través de AS2, y necesita realizar un desensamblado de una carga que no sea EDI, necesitará utilizar un mecanismo de bucle invertido con una segunda canalización de recepción. Para obtener más información, consulte [procesamiento en el lado de recepción de un mensaje no EDI entrantes a través de AS2](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md).  
  
-   La ubicación de recepción solo puede utilizar el adaptador HTTP.  
  
-   Para obtener más información sobre el procesamiento del lado de recepción de AS2, vea [cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md).  
  
-   Para obtener más información acerca del procesamiento específico que realiza el Desensamblador AS2 en la canalización de recepción, consulte [procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md).  
  
## <a name="as2-send-side-processing"></a>Procesamiento de envío de AS2  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera y envía un mensaje AS2 saliente, lo procesa en una canalización de envío AS2. Existe una canalización para enviar un mensaje EDI a través de AS2 (AS2EdiSend), que realiza el procesamiento AS2 y EDI. Otra canalización (AS2Send) realiza solo procesamiento AS2 para mensajes que no son EDI enviados a través de AS2.  
  
 El procesamiento de envío de AS2 incluye lo siguiente:  
  
-   Búsqueda de acuerdos entre socios comerciales  
  
    > [!NOTE]
    >  En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la definición de entidad incluía también la definición del acuerdo. Por lo tanto, cuando la canalización de envío buscaba las propiedades de la entidad, buscaba internamente la definición del acuerdo en la definición de la entidad y, luego, procesaba los mensajes de la forma correspondiente. Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puesto que la entidad (o socio comercial) es diferente del acuerdo entre socios comerciales, la canalización de envío busca específicamente el acuerdo entre socios comerciales.  
  
    > [!NOTE]
    >  Si se deshabilitan todos los acuerdos en los que se resuelve un mensaje, el mensaje se suspenderá.  Además, se registra una advertencia en el registro de eventos.  
  
-   Guardado de copias del mensaje en la base de datos sin repudio  
  
-   Aplicación de un sobre de AS2  
  
-   Envío de varios documentos  
  
-   Almacenamiento de cada nombre de archivo de documentos como parte de los sobre MIME  
  
-   Firma del mensaje  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite sobrescribir el certificado de firma predeterminado y usar en su lugar un certificado acordado en el acuerdo. Para obtener instrucciones sobre cómo reemplazar el certificado predeterminado para firmar mensajes salientes, consulte [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
-   Compresión del mensaje  
  
-   Cifrado del mensaje  
  
-   Cálculo de un valor MIC para el MDN  
  
-   Procesamiento de MDN entrante (en el caso de un MDN sincrónico)  
  
-   Reenvío del mensaje si no se recibe ningún MDN  
  
 Algunas de las consideraciones que debe tener en cuenta al usar el procesamiento del lado de recepción AS2 son las siguientes:  
  
-   La ubicación de envío solo puede utiliza el adaptador HTTP.  
  
-   Para obtener más información sobre el procesamiento de envío de AS2, vea [cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md).  
  
-   Para obtener más información sobre el procesamiento específico realizado en la canalización de envío, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
## <a name="see-also"></a>Vea también  
 [Rol de los acuerdos de AS2 de procesamiento](../core/the-role-of-agreements-in-as2-processing.md)   
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)   
 [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)