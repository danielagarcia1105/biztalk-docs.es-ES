---
title: "El escalado de Hosts de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f78710-93fa-4877-8273-a1634d768d88
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 843e20e76f7320555a0cfab5af5103ce3fd597d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-receiving-hosts"></a>El escalado de Hosts de recepción
Para disponer de hosts de recepción sea alta, debe tener dos o más [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos que ejecutan instancias de cada host de recepción. Mediante el escalado horizontal de los hosts de recepción puede aumentar la disponibilidad de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] las implementaciones que realizan un uso intensivo de la mensajería. Si bien estas implementaciones llevan a cabo un procesamiento mínimo de orquestación, pueden enrutar muchos mensajes de varios tipos a gran velocidad y con gran confiabilidad.  
  
 Puede mejorar la seguridad y escalabilidad del entorno separando el host de recepción de los hosts que procesan orquestaciones y envían mensajes, porque puede proteger y escalar cada host de forma independiente de otros hosts. Por ejemplo, puede agregar dos equipos (instancias de host) al host de recepción sin agregar ningún equipo a los hosts de procesamiento o envío.  
  
## <a name="understanding-in-process-and-isolated-receiving-hosts"></a>Descripción en curso y Hosts de recepción aislado  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]se integra en las aplicaciones para proporcionar servicios para la empresa. La integración se representa normalmente como [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un documento (de una aplicación), procesa el documento y envía el documento procesado a la aplicación o a otra aplicación. El proceso se denomina una transacción de documento.  
  
 Una transacción se inicia normalmente con un adaptador de BizTalk un determinado canal de protocolo de supervisión y la recepción de un documento. El *adaptador* se denomina así porque se conecta a otras aplicaciones para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Según su función, puede ser un adaptador de envío o un adaptador de recepción. La mayoría de los adaptadores de forma predeterminada es un componente de .NET con la función de recepción y la función de envío integradas en un ensamblado de .NET. En función del espacio de memoria de proceso en el que reside un adaptador, es cualquier en proceso (recepción) adaptador o un aislado (recepción) adaptador. Solo se puede hospedar un adaptador en proceso por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso (BTSNTSvc.exe) y un adaptador aislado está diseñado para ser hospedado por otro proceso. Por ejemplo, el adaptador de HTTP y el adaptador de SOAP se hospedan en el proceso de Internet Information Services (IIS). Únicamente son básicamente las extensiones ISAPI. Por otro lado, todos los adaptadores de envío son adaptadores de tipo en curso.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Configuración crea dos hosts predeterminados: el host en proceso se denomina BizTalkServerApplication y el host aislado se denomina BizTalkServerIsolatedHost. Un host puede utilizar dos funciones: uno es agrupar lógicamente la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] elementos por lo que estos elementos pueden asignarse a diferentes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesos y el otro es controlar la seguridad. Debe especificar un grupo de Windows para un host. Solo los usuarios de este grupo pueden enviar documentos a los adaptadores hospedados por el *instancias de host* asignados a este host.  
  
 Cada uno de los hosts de dos valores predeterminados tiene una instancia de host. Una instancia de host no tiene un nombre, pero está asociada a un host. La instancia de host de BizTalkServerApplication es en realidad el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (BTSNTSvc.exe) de proceso del servicio en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo dentro del grupo de BizTalk. La instancia de host BizTalkServerIsolatedHost no está enlazada directamente a un proceso. Está asociado con el proceso que aloja el adaptador de recepción.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Configuración también crea una *controlador de recepción* para cada uno de los adaptadores de forma predeterminada con la excepción de SMTP (SMTP es un adaptador de envío). Una de las propiedades del controlador de recepción es el nombre de host. Es cómo se enlaza a un host y las instancias de host de ese host.  
  
 Además de un adaptador, host, instancia de host y controlador de recepción, debe configurar un puerto de recepción antes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede empezar a recibir documentos. Un puerto de recepción contiene ubicaciones de recepción. Una ubicación de recepción tiene una propiedad de controlador de recepción. Siguiendo la lógica, puede realizar un seguimiento para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso que procesa este puerto de recepción.  
  
 En la configuración de puerto de recepción, también especificar asignaciones. En la configuración de la ubicación de recepción, debe especificar una canalización que se utilizan para preprocesar el documento. Designado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso controla todo el contenido de recibir un documento, para preprocesar el documento, para asignar el documento. Este es el mismo para las instancias de host in-process y las instancias de host aislado.  
  
## <a name="scaling-out-in-process-receiving-hosts"></a>El escalado en curso recepción hospeda  
 La siguiente ilustración muestra un [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] implementación que proporciona alta disponibilidad para las instancias del host de recepción al tener dos host cada una en un equipo diferente. Tenga en cuenta que en esta ilustración el host de procesamiento y envío no está altamente disponible, porque no hay solo una instancia de host, los elementos de BizTalk que se asigna al host de procesamiento.  
  
 ![Host múltiple para recibir los mensajes](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 Para implementaciones de gran tamaño, escenarios con varios asociados comerciales y escenarios en los que se utilizan diferentes protocolos, puede repartir la funcionalidad de recepción entre varios hosts de recepción. Por ejemplo, puede crear un host para recibir mensajes para cada adaptador, o diferentes hosts para recibir mensajes de asociados diferentes. Cuando se crean varios hosts de recepción, se pueden crear límites de seguridad y facilitar el uso y la escalabilidad del entorno; sin embargo, no se logra una alta disponibilidad del entorno. Para lograr una alta disponibilidad del entorno, debe crear dos o más instancias de host para cada host de recepción que cree. Por ejemplo, puede crear tres diferentes hosts de recepción (A, B y C) para recibir mensajes de tres compañías diferentes. Para lograr que estos hosts tengan una alta disponibilidad, debe crear instancias de host de cada uno de los hosts en dos o más equipos. Tenga en cuenta que puede tener instancias de cada host en un equipo sin perder el límite de seguridad, la facilidad de uso o la escalabilidad.  
  
 La siguiente ilustración muestra una alta disponibilidad tres equipos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno con hosts dedicados a recibir mensajes de diferentes compañías.  
  
 ![Escalado horizontal de hosts de recepción](../technical-guides/media/04bd4234-dc71-49d8-b630-0643390b29f0.gif "04bd4234-dc71-49d8-b630-0643390b29f0")  
  
 Para proporcionar alta disponibilidad en esta configuración, cada equipo ejecuta tres instancias de host: una instancia para cada una de las tres compañías. Las instancias de host de cada compañía contienen las canalizaciones y ubicaciones de recepción para comunicarse con esa compañía. Durante las operaciones típicas, siempre y cuando haya realizado el trabajo necesario para la implementación escalada delante de los adaptadores de recepción, la carga de mensajería se distribuye entre las tres instancias de cada host. Si una instancia de host en un equipo da error, las instancias de host que se ejecutan en los otros dos equipos proporcionan redundancia y mantienen la disponibilidad del servicio.  
  
## <a name="scaling-out-isolated-receiving-hosts"></a>Ajuste de escala horizontal aislada Hosts de recepción  
 Además de las instancias de host, el proceso de escalar y proporcionar alta disponibilidad para los hosts de recepción también depende de los adaptadores específicos que se implementan en su implementación. Cada adaptador tiene características específicas del protocolo que hacen que el planeamiento y la implementación sean diferentes en cada caso. Sin embargo, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] le permite aplicar la misma solución de alta disponibilidad para todos los adaptadores, principalmente a través de otros equipos e instancias de host.  
  
 Dependiendo del protocolo específico que se utilice, algunos adaptadores de recepción requieren un mecanismo adicional para distribuir los mensajes entrantes entre varios equipos host con el fin de proporcionar una alta disponibilidad. Por ejemplo, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] soluciones que utilizan el adaptador HTTP o SOAP (también conocido como el adaptador de servicios Web) requieren un equilibrador de carga como red equilibrio de carga (NLB) para distribuir la carga de trabajo de recepción, tal como se muestra en la ilustración siguiente.  
  
 ![Host de recepción de escalado horizontal aislado](../technical-guides/media/cb38ec25-bfb0-4a55-8464-b7918b6fc746.gif "cb38ec25-bfb0-4a55-8464-b7918b6fc746")  
  
 Para obtener más información sobre las directrices de alta disponibilidad para los adaptadores más comunes en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte la sección "Escalabilidad de los adaptadores de recepción de BizTalk Server" en [Scaled-Out recibir Hosts](http://go.microsoft.com/fwlink/?LinkId=151283) (http://go.microsoft.com/ ¿fwlink /? LinkId = 151283) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Clústeres de Hosts de recepción](../technical-guides/clustering-receiving-hosts.md)   
 [Ajuste de escala en Hosts de procesamiento](../technical-guides/scaling-out-processing-hosts.md)   
 [El escalado de Hosts de envío](../technical-guides/scaling-out-sending-hosts.md)