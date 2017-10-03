---
title: Ciclo de vida de un mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, orchestrations
- messages, host instances
- messages, receive locations
- send ports, about send ports
- processing, messages
- messages, processing
- host instances, about host instances
- receive locations, about receive locations
- hosts, about hosts
- messages, lifecycle
- MessageBox database, about MessageBox database
- receive ports, about receive ports
- send port groups, about send port groups
- messages, hosts
- messages, send port groups
- messages, receive ports
- orchestrations, about orchestrations
- messages, send ports
ms.assetid: d2374f86-9b5f-404f-ba7b-9cab69873fa8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05aca3ec819fb8615552c5ed57114032d7ea60b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lifecycle-of-a-message"></a>Ciclo de vida de un mensaje
La ilustración siguiente ofrece información general de alto nivel de la arquitectura de BizTalk Server desde el punto de vista de la mensajería.  
  
 ![Arquitectura de mensajería de BizTalk Server](../core/media/arch-messaging-01.gif "arch_messaging_01")  
  
 En esta vista simplificada, se recibe un mensaje a través de una ubicación de recepción definida en un puerto de recepción determinado. La ubicación de recepción procesa el mensaje y lo publica en la base de datos de cuadro de mensajes, el mecanismo principal de persistencia y enrutamiento de BizTalk Server. El cuadro de mensajes evalúa las suscripciones activas y enruta el mensaje a las orquestaciones y puertos de envío en los que coinciden las suscripciones. Las orquestaciones pueden procesar el mensaje y publica mensajes a través del cuadro de mensajes en un puerto de envío, desde donde se transportan al destino final.  
  
 A continuación se presentan los componentes principales del procesamiento de mensajes de BizTalk Server.  
  
## <a name="receive-ports-and-receive-locations"></a>Puertos de recepción y ubicaciones de recepción  
 A *puerto de recepción* es una colección de uno o más ubicaciones de recepción que definen puntos de entrada específicos en BizTalk Server. A *ubicación de recepción* es la configuración de un solo punto de conexión (URL) para recibir mensajes. La ubicación contiene la información de configuración para el adaptador de recepción y la canalización de recepción. El *adaptador* es responsable de la parte de transporte y las comunicaciones de recibir un mensaje. Entre los ejemplos se incluyen el adaptador de archivo y el adaptador de SOAP, que reciben mensajes desde distintas procedencias. La canalización de recepción se encarga de la preparación del mensaje para su publicación en el cuadro de mensajes. A *canalización* es una serie de componentes que se ejecutan en secuencia, cada uno con el procesamiento específico de un mensaje como cifrado y descifrado, análisis o validación. Para obtener más información acerca de las canalizaciones, puertos de recepción y ubicaciones de recepción, consulte [artefactos](../core/artifacts.md).  
  
## <a name="send-ports-and-send-port-groups"></a>Puertos de envío y grupos de puertos de envío  
 A *puerto de envío* es la combinación de una canalización de envío y un adaptador de envío. Un grupo de puertos de envío representa un conjunto de puertos de envío y funciona como una lista de distribución de mensajes de correo electrónico. Cuando se envía un mensaje a un grupo de puertos de envío, dicho mensaje se enviará a todos los puertos de envío del grupo. La canalización de envío sirve para preparar un mensaje procedente de BizTalk Server para transmitirlo a otro servicio. El adaptador de envío se encarga de enviar el mensaje con un protocolo específico, como, por ejemplo, SOAP o FTP. Para obtener más información sobre los puertos de envío y grupos de puertos de envío, consulte [artefactos](../core/artifacts.md).  
  
## <a name="orchestrations"></a>Orquestaciones  
 Las orquestaciones pueden realizar suscripciones para recibir y publicar (enviar) mensajes a través del cuadro de mensajes. Además, las orquestaciones pueden construir nuevos mensajes. Los mensajes se reciben con el mecanismo de suscripción de enrutamiento ya mencionado. Cuando se completan las suscripciones para las orquestaciones, se activa una nueva instancia y el mensaje se entrega, o, en caso de que se trate de suscripciones de instancia, la instancia vuelve a hidratarse si es necesario y el mensaje se entrega. Cuando se envían mensajes desde una orquestación, que se publican en el cuadro de mensajes de la misma manera como un mensaje que llega a una ubicación de recepción con las propiedades adecuadas se inserta en la base de datos para su uso en el enrutamiento. Para obtener más información acerca de las orquestaciones, consulte [artefactos](../core/artifacts.md).  
  
## <a name="messagebox-database"></a>Base de datos de cuadro de mensaje  
 El núcleo del motor de suscripción o publicación de BizTalk Server es la base de datos de cuadro de mensajes. El cuadro de mensajes está formada por dos componentes: una o más bases de datos de Microsoft SQL Server y el agente de mensaje. La base de datos de SQL Server proporciona el almacén de persistencia para numerosos componentes, entre los que se incluyen mensajes, propiedades de mensaje, suscripciones, estados de orquestación, datos de seguimiento y colas de hosts para el enrutamiento. Para obtener más información acerca de la base de datos de cuadro de mensajes, vea [la base de datos de cuadro de mensajes](../core/the-messagebox-database.md).  
  
## <a name="hosts-and-host-instances"></a>Host e instancias de host  
 A *host* es una representación lógica de un proceso de Microsoft Windows que ejecuta artefactos de BizTalk Server como puertos de envío y orquestaciones. A *instancia de host* es la representación física de un host en un servidor específico. Existen dos tipos de host: el host de tipo En curso, propiedad de BizTalk Server y administrado por él, o el host aislado, que implica que el código de BizTalk Server se está ejecutando en un proceso no controlado por BizTalk Server. Un buen ejemplo de host aislado es Internet Information Services (IIS), que aloja las funciones de recepción de los adaptadores de HTTP y SOAP. Los hosts se definen para un grupo de BizTalk Server completo, un conjunto de servidores BizTalk Server que comparten configuración, cuadros de mensajes, puertos, etc. Para obtener más información sobre los hosts y las instancias de host, consulte [entidades](../core/entities.md).  
  
## <a name="saving-a-message-body"></a>Guardar un cuerpo de mensaje  
 Hay tres formas de guardar un cuerpo de mensaje.  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a>Desde las consultas de la página del concentrador de grupo del MMC de administradores  
 Este método solo es para los mensajes de la base de datos de cuadro de mensajes.  
  
-   Visualización de una instancia de servicio.  
  
-   Abra la **detalles de la instancia de servicio** cuadro de diálogo.  
  
-   Haga clic en el **ficha mensajes** para ver la lista de mensajes asociados a esta instancia.  
  
-   Haga clic en el mensaje y, a continuación, haga clic en **guardar**.  
  
     -O bien-  
  
-   Haga doble clic en el mensaje para abrirlo en el **Visor de mensajes de**y haga clic en **guardar**.  
  
### <a name="from-the-operations-om"></a>Desde el modelo de objetos de operaciones  
  
-   Use **GetInstance** para recuperar un objeto de instancia del servicio.  
  
-   Use **Instance.Messages []** para enumerar todos los mensajes que actualmente hace referencia a la instancia de servicio.  
  
-   Usar métodos en el objeto de mensaje como **Message.BodyPart []** y **Message.Context []** para tener acceso y guardarlo.  
  
### <a name="from-the-dta"></a>Desde DTA  
  
-   Recuperar mensajes de DTA mediante la **GetTrackedInstance** y **GetTrackedmessage** llamadas API.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)