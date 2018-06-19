---
title: Procesamiento de EDI en BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc60423-24b6-4920-a870-520f575085ed
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b68781707211922d7d29958f896608c87358c7c0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008685"
---
# <a name="edi-processing-in-biztalk-server"></a>Procesamiento de EDI en BizTalk Server
En este tema se proporciona información general del procesamiento en el lado de recepción y en el lado de envío de mensajes EDI, y la forma en que los acuerdos de socios comerciales pueden ayudar a conseguir la mensajería de EDI.  
  
## <a name="trading-partner-agreements-for-edi-processing"></a>Acuerdos de socios comerciales para el procesamiento EDI  
 Acuerdos de socios comerciales desempeñan un papel clave en la compatibilidad EDI en BizTalk Server. La mayoría de las funciones administrativas y de configuración relacionadas con el procesamiento de EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se realizan mediante la configuración de acuerdos entre socios comerciales para los perfiles de negocio. Los acuerdos unen propiedades comunes de procesamiento de mensaje bidireccionales de perfiles específicos del negocio de ambos socios. Los acuerdos se basan en la configuración de protocolo definida para cada perfil de negocio. Para implementar un acuerdo entre socios comerciales de dos perfiles de negocio, debe definir propiedades para cada perfil de negocio que va a intercambiar mensajes. Las propiedades de cada perfil de negocio se establecen como un receptor de intercambio y un remitente de intercambio. Para procesar un mensaje entrante o generar un mensaje saliente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe conocer el acuerdo en el que se resuelve, y el esquema que se aplica al mensaje. Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede determinar el acuerdo, usará las propiedades definidas en la interfaz TPM para el acuerdo de socios comerciales de reserva.  
  
 Existen dos conjuntos principales de opciones de protocolo de codificación en TPM: uno para propiedades de EDIFACT y otro para propiedades de X12. Los dos conjuntos de propiedades cuentan con muchos paralelismos. Para obtener más información acerca de la configuración del protocolo, vea [configuración del protocolo](../core/protocol-settings.md). Para obtener más información acerca de los acuerdos, vea [acuerdo de socios comerciales](../core/trading-partner-agreement.md). La configuración del protocolo y el acuerdo de socios comerciales se establece en la interfaz de usuario de Administración de socios comerciales (TPM). Las pantallas TPM se encuentran en el **partes** nodo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. No tiene que ser un programador para configurar el procesamiento de EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para obtener más información sobre los acuerdos entre socios comerciales cómo ayudan en el procesamiento de EDI, vea [el rol de los acuerdos en el procesamiento de EDI](../core/the-role-of-agreements-in-edi-processing.md).  
  
## <a name="edi-receive-side-processing"></a>Procesamiento de recepción de EDI  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje EDI, procesa el mensaje en la canalización de recepción EDI. La canalización de recepción lleva a cabo el siguiente procesamiento básico:  
  
-   Búsqueda de acuerdo y determinación de esquema de socio comercial.  
  
    > [!NOTE]
    >  En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la definición de entidad incluía también la definición del acuerdo. De este modo, cuando la canalización de recepción buscaba las propiedades de la entidad, buscaba internamente la definición del acuerdo dentro de la definición de la entidad y, a continuación, procesaba los mensajes de forma correspondiente. Con BizTalk Server, porque la entidad (o socio comercial) es distinto del acuerdo entre socios comerciales, la canalización de recepción busca el acuerdo de socio comercial concreto.  
  
    > [!NOTE]
    >  Si se deshabilitan todos los acuerdos en los que se resuelve un mensaje, el mensaje se suspenderá. Además, se registra una advertencia en el registro de eventos.  
  
-   Si un solo mensaje EDI contiene varios intercambios, divide los intercambios y procesa cada uno por separado (si está habilitada esta opción). Para obtener más información, consulte [habilitar la recepción de varios intercambios en un único mensaje](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md).  
  
-   Analiza cada intercambio EDI, convirtiendo los datos con codificación X12 o EDIFACT en un documento XML.  
  
-   Valida el sobre y su mensaje según los estándares EDI, el acuerdo de socio y los esquemas de mensaje.  
  
-   Si el intercambio se procesa por lotes, bien divide el intercambio por lotes creando un archivo XML para cada conjunto de transacciones y promocionando las propiedades necesarias para el procesamiento por lotes, o bien conserva el intercambio.  
  
-   Genera una confirmación.  
  
-   Convierte el sobre EDI en propiedades de contexto y promociona otras propiedades para el procesamiento de EDI.  
  
-   Promociona las propiedades que controlan el procesamiento por lotes. Esto puede incluir el envío de conjuntos de transacciones sin lotes a diversas entidades.  
  
 Algunas de las consideraciones que debe tener en cuenta al usar el procesamiento del lado de recepción EDI son las siguientes:  
  
-   La ubicación de recepción puede usar cualquier tipo de transporte.  
  
-   Para obtener más información sobre el procesamiento del lado de recepción de EDI, vea [cómo BizTalk Server recibe mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md).  
  
-   Para obtener más información acerca del procesamiento específico que realiza el Desensamblador EDI en la canalización de recepción, consulte [cómo funciona el de desensamblador de EDI](../core/how-the-edi-disassembler-works.md).  
  
## <a name="edi-batch-processing"></a>Procesamiento por lotes de EDI  
 Si el mensaje entrante es un lote, la canalización de recepción EDI dividirá el intercambio por lotes en los conjuntos de transacciones que lo forman, o conservará el intercambio por lotes, según la configuración. La canalización EDIReceive usa el componente de canalización BatchMarker para enrutar cualquier intercambio que se vaya a agrupar en lotes a la orquestación de procesamiento por lotes o a la orquestación de enrutamiento.  
  
 Tras el procesamiento de recepción, la orquestación de procesamiento por lotes procesará los conjuntos de transacciones que se vayan a agrupar en lotes para su envío. La orquestación de procesamiento por lotes creará un lote según los criterios de filtro, un intervalo de activación y los criterios de versión.  
  
 Si los conjuntos de transacciones EDI que no se procesan por lotes se deben enviar a lotes, una orquestación de enrutamiento procesará los conjuntos de transacciones. Se creará una copia del conjunto de transacciones para cada lote coincidente.  
  
 Para obtener más información acerca del procesamiento específico realizado en los lotes, vea [de procesamiento por lotes entrantes](../core/processing-incoming-batches.md) o [de procesamiento por lotes los mensajes EDI salientes](../core/batching-outgoing-edi-messages.md).  
  
## <a name="edi-send-side-processing"></a>Procesamiento de envío de EDI  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera y envía un mensaje EDI saliente, procesa el mensaje en la canalización de envío EDI. La canalización de envío lleva a cabo el siguiente procesamiento:  
  
-   Búsqueda de acuerdo y determinación de esquema de socio comercial.  
  
    > [!NOTE]
    >  En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la definición de entidad incluía también la definición del acuerdo. Por lo tanto, cuando la canalización de envío buscaba las propiedades de la entidad, buscaba internamente la definición del acuerdo en la definición de la entidad y, luego, procesaba los mensajes de la forma correspondiente. Con BizTalk Server, porque la entidad (o socio comercial) es distinto del acuerdo entre socios comerciales, la canalización de envío busca el acuerdo de socio comercial concreto.  
  
    > [!NOTE]
    >  Si se deshabilitan todos los acuerdos en los que se resuelve un mensaje, el mensaje se suspenderá.  Además, se registra una advertencia en el registro de eventos.  
  
-   Serializa el mensaje EDI, convirtiendo el documento XML en datos con codificación X12 o EDIFACT.  
  
-   Si los datos del mensaje contienen caracteres que también se usan como separadores X12, la canalización de envío se puede configurar para que sustituya los caracteres de la carga por otro carácter.  
  
-   Si el mensaje EDI es un intercambio por lotes, la canalización de envío toma el intercambio del cuadro de mensaje de BizTalk después de que la orquestación de procesamiento por lotes haya creado el lote.  
  
-   Valida el mensaje saliente.  
  
-   Crea el sobre EDI según las propiedades de la entidad o las propiedades de sobre EDI especificadas en tiempo de ejecución.  
  
-   Procesa las confirmaciones recibidas.  
  
 Algunas consideraciones que debe tener en cuenta al usar el procesamiento del lado de envío de EDI son las siguientes:  
  
-   El puerto de envío puede usar cualquier tipo de transporte.  
  
-   Para obtener más información sobre el procesamiento de envío EDI, vea [cómo BizTalk Server envía mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md).  
  
-   Para obtener más información sobre el procesamiento específico realizado en la canalización de envío, consulte [cómo funciona el de ensamblador de EDI](../core/how-the-edi-assembler-works.md).  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad EDI en BizTalk Server](../core/edi-support-in-biztalk-server1.md)   
 [Problemas de soporte técnico EDI](../core/edi-support-issues.md)   
 [Rol de los acuerdos en el procesamiento de EDI](../core/the-role-of-agreements-in-edi-processing.md)   
 [Cómo BizTalk Server recibe mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)   
 [Cómo BizTalk Server envía mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)   
 [Desarrollo y configuración de soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)