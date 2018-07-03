---
title: Conectar sistemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c4895e5-7272-415f-a0de-905256fa0a43
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a151fb5c6247b8630ab423054adef42e64efd06a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995597"
---
# <a name="connecting-systems"></a>Conectar sistemas
El intercambio eficaz de mensajes a través de distintos sistemas de software en equipos diferentes es un requisito indispensable para la integración. Dada la diversidad de estilos de comunicación que existen, BizTalk Server debe admitir una variedad de protocolos y formatos de mensaje. Como se describe más adelante, una parte importante de este motor se dedica a este trabajo de comunicación. No obstante, un aspecto importante que se ha de tener en cuenta es que el motor sólo trabaja con documentos XML de forma interna. Independientemente del formato en el que llegue el mensaje, debe convertirse a XML. Del mismo modo, si el destinatario del documento no puede aceptarlo en XML, el motor lo convierte en el formato esperado por el destino.  
  
## <a name="sending-and-receiving-messages-adapters"></a>Enviar y recibir mensajes: adaptadores  
 Porque BizTalk Server debe hablar con una variedad de software, se basa en los adaptadores para hacer esto posible. Un adaptador es una implementación de un mecanismo de comunicación, como, por ejemplo, un protocolo determinado. Los programadores determinan los adaptadores que se utilizarán en situaciones determinadas. Podría elegir uno de los adaptadores integrados que proporciona BizTalk Server, por ejemplo, use un adaptador creado para un producto conocido como Windows SharePoint Services o incluso crear un adaptador personalizado. En todos estos casos, el adaptador se integra en una base estándar, denominada Marco de trabajo de adaptadores. Este marco de trabajo ofrece una manera común de crear y ejecutar adaptadores, y admite las mismas herramientas que se utilizan para administrar todos los tipos de adaptadores.  
  
 Microsoft BizTalk Server incluye los siguientes adaptadores nativos:  
  
- Adaptador de archivo: admite leer y escribir en archivos en el sistema de archivos de Windows. Puesto que las aplicaciones implicadas en un proceso empresarial pueden tener acceso con frecuencia al mismo sistema de archivos, tanto de forma local como a través de una red, el intercambio de mensajes por medio de los archivos puede resultar una opción práctica.  
  
- Adaptador de FTP: admite el envío y recepción de información entre un servidor de protocolo de transferencia de archivos (FTP) y BizTalk Server.  
  
- Adaptador de HTTP: admite el envío y recepción de información mediante HTTP. BizTalk Server expone una o varias direcciones URL para permitir que otras aplicaciones enviar datos a él, y puede utilizar este adaptador para enviar datos a otras direcciones URL.  
  
- Adaptador de MSMQ: admite el envío y recepción de mensajes mediante Microsoft Message Queuing (MSMQ).  
  
- Adaptador de WebSphere MQ: admite el envío y recepción de mensajes mediante IBM WebSphere MQ (conocido anteriormente como MQSeries).  
  
- Adaptador de POP3: admite la recepción de mensajes de correo electrónico y sus datos adjuntos con la versión tres del protocolo de oficina de correos (POP3).  
  
- Adaptador de SMTP: admite el envío de mensajes mediante SMTP. Las direcciones de correo electrónico estándar sirven para identificar las entidades.  
  
- Adaptador de SOAP: admite el envío y recepción de solicitudes de servicio Web para habilitar el servidor BizTalk Server para conectarse a servicios Web.  
  
- Adaptadores de WCF: admite el envío y recepción de información mediante Windows Communication Foundation.  
  
- Adaptador de Windows SharePoint Services (WSS): admite el acceso y publicación de documentos almacenados en bibliotecas de documentos de Microsoft Windows SharePoint.  
  
  Los adaptadores del software empresarial más actualizado también se encuentran disponibles en Microsoft, y entre ellos se incluyen:  
  
- Adaptador de Microsoft BizTalk para JD Edwards OneWorld  
  
- Adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne  
  
- Adaptador de Microsoft BizTalk para PeopleSoft Enterprise  
  
- Adaptador de Microsoft BizTalk para TIBCO Rendezvous  
  
- Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service  
  
  Para obtener más información acerca de estos adaptadores, vea [adaptadores de BizTalk Server](../core/adapters-in-biztalk-server.md).  
  
  Independientemente del adaptador que se emplee para recibir datos, normalmente los mensajes recibidos deben procesarse antes de que ninguna orquestación pueda obtener acceso a ellos. De igual modo, a menudo es necesario procesar los mensajes salientes producidos por una orquestación antes de que el adaptador los envíe.  
  
## <a name="processing-messages-pipelines"></a>Procesamiento de mensajes: canalizaciones  
 Las aplicaciones subyacentes a un proceso empresarial se comunican mediante el intercambio de varios tipos de documentos: por ejemplo, mediante pedidos y facturas. Para que una aplicación de BizTalk Server ejecutar un proceso empresarial, debe ser capaz de procesar correctamente los mensajes que contienen estos documentos. Este procesamiento puede constar de varias fases, de ahí que la realice una canalización de mensajes. Los mensajes entrantes se procesan a través de una canalización de recepción, mientras que los salientes pasan a través de una canalización de envío.  
  
 Por ejemplo, aunque más aplicaciones que se va a diseñadas para admitir los documentos XML, muchas, probablemente la mayoría de hoy en día, no puede. Dado que BizTalk Server sólo funciona con documentos XML internamente, debe proporcionar una forma de convertir otros formatos a y desde XML. Además, es posible que deba cubrir otros servicios, como, por ejemplo, la autenticación del remitente de un mensaje. Para tratar éstas y otras tareas de una forma independiente y personalizada, se crea una canalización con un número de etapas. Cada una de ellas contiene uno o varios componentes de modelo de objetos componentes (COM) o compatibles con .NET. Cada componente se encarga de una parte determinada del procesamiento del mensaje. BizTalk Server proporciona varios componentes estándares que abordan los casos más comunes. Si éstos no son suficientes, los programadores también pueden crear componentes personalizados para las canalizaciones de recepción y envío.  
  
 ![](../core/media/understandingbts-05-pipelinereceive.gif "UnderstandingBTS_05_PipelineReceive")  
  
 La ilustración anterior muestra las fases de una canalización de recepción, así como los componentes estándar que se proporcionan para cada una. Estas fases y sus componentes asociados son los siguientes:  
  
- Descodificar: BizTalk Server proporciona un componente estándar para esta fase, el descodificador MIME/SMIME. Este componente puede controlar mensajes y los datos adjuntos que contengan en formatos MIME o Secure MIME (S/MIME). El componente convierte los dos tipos de mensajes en XML, y puede descifrar mensajes en formato S/MIME y comprobar las firmas digitales.  
  
- Desensamblar: Se proporcionan tres componentes estándar. El componente Desensamblador de archivos sin formato convierte este tipo de archivos en documentos XML. Estos archivos pueden ser posicionales (cada registro tiene la misma longitud y estructura) o delimitados (se utiliza un carácter designado para separar los registros del archivo). El segundo componente estándar, el Desensamblador de XML, analiza los mensajes entrantes que se han descrito como mensajes con formato XML. El tercer componente estándar, muy poco utilizado en la actualidad, es el Desensamblador de BizTalk Framework. Este componente acepta los mensajes enviados con el confiable mecanismo de mensajería definido por BizTalk Framework, que se implementó en BizTalk Server 2000.  
  
- Validar: BizTalk Server proporciona un componente de validador de XML para esta fase. Como su propio nombre indica, este componente valida un documento XML producido en la fase de desensamblado. Para ello, toma como base un esquema o un grupo de esquemas especificado y, si el documento no cumple con uno de estos esquemas, devuelve un error.  
  
- Resolver entidad: el único componente estándar para esta fase, resolución de entidades, intenta determinar una identidad para el remitente del mensaje. Si el mensaje se ha firmado digitalmente, la firma se usa para buscar una identidad de Windows en la base de datos de administración de BizTalk Server. (Como se describe más adelante, esta base de datos también se utiliza con herramientas de administración de BizTalk Server.) Si el mensaje contiene el identificador de seguridad autenticado (SID) de un usuario de Windows, se usa esta identidad. Si no se consigue aplicar ningún mecanismo, se le asignará al remitente del mensaje una identidad anónima predeterminada.  
  
  ![](../core/media/understandingbts-06-pipelinesend.gif "UnderstandingBTS_06_PipelineSend")  
  
  Los mensajes salientes también pueden pasar por varias fases, según establezca la canalización de envío que se utilice. La ilustración anterior muestra las fases y los componentes estándar de una canalización de envío. Estas sobrecargas son:  
  
- No preensamblar: Se proporcionan componentes estándar. En su lugar pueden instalarse componentes personalizados en función de sus necesidades.  
  
- Ensamblar: Al igual que la fase de desensamblado de una canalización de recepción, esta fase tiene también tres componentes estándar. El Ensamblador de archivos sin formato convierte un mensaje XML en un archivo sin formato de tipo posicional o delimitado, mientras que el Ensamblador de XML permite agregar un sobre al mensaje XML saliente y realizar otros cambios en él. La tercera opción, el Ensamblador de BizTalk Framework, empaqueta los mensajes con la tecnología de mensajería de BizTalk Framework para enviarlos de forma confiable.  
  
- Codificar: BizTalk Server define sólo un componente estándar para esta fase, el codificador MIME/SMIME. Este componente empaqueta los mensajes salientes en formato MIME o S/MIME. Si se utiliza S/MIME, el mensaje también puede firmarse o cifrarse digitalmente.  
  
  BizTalk Server define algunas canalizaciones predeterminadas, incluido un par de envío y recepción que se puede usar para controlar los mensajes que ya estén expresados en XML. Asimismo, cualquier programador puede crear canalizaciones personalizadas gracias al Diseñador de canalizaciones. Esta herramienta, que se ejecuta en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], proporciona una interfaz gráfica que permite que el programador mueva los componentes con la opción de arrastrar y soltar para crear canalizaciones con el comportamiento necesario.  
  
## <a name="choosing-messages-subscriptions"></a>Seleccionar mensajes: suscripciones  
 Una vez que se transmite un mensaje por un adaptador y una canalización de recepción, el paso siguiente consiste en determinar su destino. Un mensaje con más frecuencia está dirigido a una orquestación, pero también es posible que un mensaje ir directamente a una canalización de envío, permitiendo a BizTalk Server que se usará como puramente un sistema de mensajería. En ambos casos, la correspondencia entre los mensajes y sus destinos se realiza mediante subscripciones.  
  
 Cuando una canalización de recepción procesa un mensaje, crea un contexto de mensaje que contiene varias propiedades del mensaje. Una orquestación o una canalización de envío puede suscribir mensajes en función de los valores de estas propiedades. Por ejemplo, una orquestación puede crear una suscripción que coincide con todos los mensajes del tipo "Factura" recibido de la empresa QwickBank o todos los mensajes del tipo "Factura" recibido de la empresa QwickBank o todos los mensajes del tipo "Factura", que son más de 10.000 $. Sin embargo, se especifica, devuelve una suscripción en su suscriptor sólo los mensajes que coinciden con los criterios que define la suscripción. Un mensaje recibido puede iniciar un proceso empresarial creando una instancia de alguna orquestación, o puede activar otro paso en un proceso empresarial que ya esté en ejecución. De igual modo, cuando una orquestación envía un mensaje, éste se envía a una canalización de envío en función de una suscripción que haya establecido esa canalización.  
  
-   En BizTalk Server, también es posible suscribirse a las condiciones de error específico. Un mensaje de error puede procesarse de una forma determinada o moverse a un destino concreto, como, por ejemplo, a una carpeta de Windows SharePoint Services.  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería de BizTalk Server](../core/the-biztalk-server-messaging-engine.md)   
 [Publicar y suscribirse de arquitectura](../core/publish-and-subscribe-architecture.md)   
 [Adaptadores](../core/adapters.md)   
 [Canalizaciones](../core/pipelines.md)