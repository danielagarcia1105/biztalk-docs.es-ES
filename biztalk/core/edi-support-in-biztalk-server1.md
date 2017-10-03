---
title: Compatibilidad con EDI en BizTalk Servidor1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cddab7a-99ef-4dbb-bb74-9e3d03df3996
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5edfa2eccfeac9a4d4192b2189877081ddf25a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-support-in-biztalk-server"></a>Compatibilidad con EDI en BizTalk Server
En este tema se ofrece una breve información general de EDI y cómo [!INCLUDE[prague](../includes/prague-md.md)] es compatible con EDI.  
  
## <a name="introduction-to-edi"></a>Introducción a EDI  
 El intercambio electrónico de datos (EDI) es uno de los medios usados frecuentemente a través del cual los socios comerciales intercambian datos de forma electrónica. EDI está orientado principalmente a la mensajería. Los documentos se implementan como archivos sin formato que pueden incluir conjuntos de transacciones por lotes. Los intercambios por lotes pueden contener varios grupos y cada uno de éstos puede contener a su vez varios mensajes o conjuntos de transacciones.  
  
 EDI está formado por métodos específicos de intercambio de datos acordados por organismos de estandarización. Los estándares EDI más importantes son X12 (estandarizado por ANSI y usado principalmente en Norteamérica) y EDIFACT (estandarizado por las Naciones Unidas y usado principalmente en todo el mundo). Otros estándares derivan de los mencionados. Por ejemplo, HIPAA deriva de X12 y KEDIFACT, en Corea, de EDIFACT. Los estándares son muy parecidos a la estructura de mensaje y a los esquemas de confirmación, pero cuentan con diferencias distintivas.  
  
 Los estándares EDI recomiendan:  
  
-   Los formatos, los juegos de caracteres y los elementos de datos usados en el intercambio de documentos  
  
-   Los sobres usados en la transacción EDI  
  
-   Las confirmaciones requeridas para comprobar la entrega  
  
-   Cómo proporcionar una entrega garantizada exactamente una vez, una detección automática y un informe de datos incorrectos o dañados.  
  
 Mientras que los estándares EDI establecen las reglas respecto a la estructura del documento, los socios comerciales deben acordar la información específica que se transmitirá y cómo debe usarse esta información. El diseño de un sistema EDI que conecta dos socios comerciales viene determinado por lo que requieren los estándares y por lo que acuerdan los socios comerciales. Para obtener más información acerca de la mensajería EDI, vea [mensajería EDI](../core/edi-messaging.md).  
  
> [!NOTE]
>  Los mensajes EDI se distinguen de su transporte. Los estándares EDI no recomiendan el transporte de mensaje. Además, los mensajes EDI pueden enviarse utilizando diferentes medios.  
  
## <a name="how-edi-is-implemented-in-biztalk-server"></a>Implementar EDI en BizTalk Server  
 [!INCLUDE[prague](../includes/prague-md.md)] incluye funcionalidad nativa que proporciona compatibilidad para EDI. EDI está incorporado en el producto; no es un complemento, por ejemplo, un adaptador o una tecla de aceleración.  
  
 **Procesamiento de intercambio**  
  
 La característica EDI realiza el siguiente procesamiento de envío y recepción en canalizaciones que hace cumplir las reglas exigidas por los estándares EDI.  
  
-   Procesa mensajes EDI entrantes, incluida la validación de intercambios y la generación de confirmaciones  
  
-   Genera y envía mensajes EDI salientes, incluida la validación de intercambios y el procesamiento de confirmaciones recibidas, en función de la configuración.  
  
 **Procesamiento por lotes**  
  
 La canalización de recepción y la orquestación administran el procesamientos por lotes:  
  
-   Si se va a dividir un intercambio por lotes recibido, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo divide en los conjuntos de transacciones que lo componen, además de generar un archivo XML para cada conjunto y promocionar las propiedades necesarias para la generación por lotes de envío.  
  
-   Si se va a conservar un intercambio por lotes recibido, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el lote de tal manera que mantiene los grupos y conjuntos de transacciones que contenía cuando se recibió el lote.  
  
-   Si se va a configurar un intercambio por lotes recibido, los lotes reciben grupos y conjuntos de transacciones EDI en un intercambio saliente.  
  
-   Si varias entidades se suscriben a un intercambio por lotes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía una copia del lote a cada entidad.  
  
 **Acuerdos de socios comerciales**  
  
 Los socios comerciales definen entre ellos el acuerdo entre socios comerciales, formado por un conjunto de propiedades definidas en la consola de administración de BizTalk Server. Estas propiedades de entidades, además de las propiedades de ubicaciones y puertos de envío y recepción, determinan el procesamiento EDI de envío y recepción. Para obtener más información acerca de acuerdos de socios comerciales, vea [acuerdo de socios comerciales](../core/trading-partner-agreement.md).  
  
 **Estado del intercambio**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona la notificación de estado específica de EDI. Estos informes de estado proporcionan información completa sobre el estado de una transacción de intercambio de un documento, incluidas las confirmaciones correlacionadas con el intercambio.  
  
## <a name="edi-components-in-biztalk-server"></a>Componentes de EDI en BizTalk Server  
 Los componentes Microsoft [!INCLUDE[prague](../includes/prague-md.md)] usados para el procesamiento de EDI incluyen los siguientes:  
  
-   La aplicación EDI de BizTalk contiene artefactos (que incluyen canalizaciones, orquestaciones y esquemas) que se necesitan para procesar documentos EDI.  
  
    > [!NOTE]
    >  Cuando se configura la característica EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el programa de configuración crea esta aplicación. Siempre que cree una aplicación que procesará intercambios EDI, debe agregar una referencia a la aplicación EDI de BizTalk desde su aplicación. Para obtener más información, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
-   La canalización de recepción EDI de BizTalk (canalización EdiReceive) analiza los documentos con codificación EDI, divide lotes de EDI, convierte documentos con codificación EDI en codificación XML, lleva a cabo la validación EDI y XSD así como la división de subdocumentos HIPAA X12. Para obtener más información, consulte [componentes de recepción EDI](../core/edi-receive-components.md).  
  
-   La canalización de envío EDI de BizTalk (canalización EdiSend) convierte documentos XML en codificación X12 o EDIFACT, serializa documentos con codificación EDI y lleva a cabo la validación EDI y XSD. Para obtener más información, consulte [componentes de envío EDI](../core/edi-send-components.md).  
  
-   La interfaz de usuario Administración de socios comerciales (TPM) permite establecer las propiedades de procesamiento para socios comerciales comprometidos con el intercambio EDI de documentos y el transporte AS2 de documentos. Para obtener más información, consulte [el rol de los acuerdos en el procesamiento de EDI](../core/the-role-of-agreements-in-edi-processing.md) y **EDI y AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
-   La orquestación por lotes procesa por lotes los intercambios EDI y define propiedades de contexto para el envío del intercambio por lotes. La orquestación de enrutamiento controla las instancias en las que los mensajes coinciden con varios lotes y crea el número necesario de copias del mensaje. Para obtener más información, consulte [de procesamiento por lotes entrantes](../core/processing-incoming-batches.md) y [de procesamiento por lotes los mensajes EDI salientes](../core/batching-outgoing-edi-messages.md).  
  
-   La interfaz de usuario de informes de estado proporciona información completa sobre los intercambios EDI y las confirmaciones correlacionadas. Para obtener más información, consulte [EDI y los informes de estado de AS2](../core/edi-and-as2-status-reporting.md).  
  
-   Las herramientas de tiempo de diseño de Visual Studio le permiten generar y validar una instancia, validar un esquema y, además, probar y validar una asignación. Para obtener más información, consulte [herramientas XML en tiempo de diseño usando](../core/using-design-time-xml-tools.md).  
  
-   Un repositorio de esquema incluye X12, EDIFACT, HIPAA X12N 4010A XSD, EANCOM y esquemas de control. Para obtener más información, consulte [compatibilidad del esquema de documento EDI](../core/edi-document-schema-support.md).  
  
-   Una herramienta de migración (herramienta de migración de entidades) permite migrar datos de entidades EDI de BizTalk Server 2006 R2 o BizTalk Server 2009 a [!INCLUDE[prague](../includes/prague-md.md)]. Para obtener más información, consulte [migrar artefactos de EDI desde una versión anterior de BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de EDI en BizTalk Server](../core/edi-processing-in-biztalk-server.md)   
 [Compatibilidad con HIPAA en BizTalk Server](../core/hipaa-support-in-biztalk-server.md)   
 [Problemas de soporte técnico EDI](../core/edi-support-issues.md)   
 [Arquitectura de la solución EDI](../core/edi-solution-architecture.md)   
 [EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md)   
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)