---
title: Tutoriales de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, getting started
- getting started, tutorials
ms.assetid: 58019f98-e91a-4705-b689-c269174d6bae
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f13a5d74d0957a208600653823e7604680296f4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232076"
---
# <a name="biztalk-server-tutorials"></a>Tutoriales de BizTalk Server
Tutoriales para aprender a usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].

Los tutoriales de BizTalk Server contienen escenarios sencillos para que los usuarios nuevos adquieran cierta experiencia en el empleo de una variedad de herramientas de BizTalk, a la vez que crean soluciones de integración compiladas que pueden someterse a prueba. Para los usuarios más avanzados, o los usuarios que diseñan soluciones de BizTalk, consulte [escenarios para soluciones empresariales](../core/scenarios-for-business-solutions.md).  
  
## <a name="enterprise-application-integration"></a>Enterprise Application Integration
  
[Tutorial: Integración de aplicaciones empresariales](../core/tutorial-1-enterprise-application-integration.md) 

Implementar una solución de BizTalk que reciba mensajes de solicitud de reposición de inventario de un almacén y evalúe los mensajes de solicitud. Si la solución rechaza una solicitud, envía un mensaje de rechazo al almacén. Si la solución aprueba una solicitud, a continuación, reenvía el mensaje a un sistema de planeamiento de recursos empresariales (ERP).  

## <a name="create-a-hybrid-application"></a>Crear una aplicación híbrida
[Tutorial: Crear una aplicación híbrida mediante BizTalk Server](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

Configurar una aplicación de extremo a extremo que usa EDI para generar confirmaciones, Bus de servicio para recibir mensajes, y, a continuación, insertar datos en SQL. 

## <a name="invoke-a-rest-interface"></a>Invocar una interfaz REST
[Tutorial: Invocar una interfaz REST con BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

Usa el adaptador de WCF-WebHttp para utilizar una dirección URL de REST y, a continuación, enviar un mensaje de respuesta. 

## <a name="integrate-biztalk-with-salesforce"></a>Integrar BizTalk con Salesforce
[Tutorial: Integrar el servidor BizTalk Server con Salesforce](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

Cada vez que se crea una oportunidad de venta en el sistema Salesforce, Northwind quiere que sus sistemas locales, por ejemplo, BizTalk Server, para recibir una notificación para que otros sistemas de nivel inferiores pueden recopilar datos e iniciar otros procesos relevantes. 

## <a name="process-json-messages"></a>Procesar mensajes JSON
[Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)  

Configurar una aplicación de BizTalk que recibe un pedido de compra JSON. En la canalización de recepción, un componente de descodificador JSON transforma el mensaje JSON para XML. A continuación, utiliza una asignación para transformar el pedido de compra XML en una factura XML. La canalización de envío utiliza un codificador JSON para transformar la factura XML en una factura JSON y, a continuación, envía el mensaje.

## <a name="edi-interface-developer"></a>Programadores de la interfaz EDI
  [Tutorial: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
Un socio comercial envía pedidos de compra con ANSI X12 4010 (un mensaje 850) del conjunto de transacciones 850. Pedidos de compra de un proceso de sistema de orden interno.

Como desarrollador Interfaz responsable de diseñar la interfaz entre el mensaje 850, recibe de su socio comercial y sistema de pedidos interno de su empresa. Su socio comercial requiere una confirmación funcional (997) para cada mensaje 850 que envía.


## <a name="as2"></a>ENVÍO/RECEPCIÓN  
[Tutorial: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md)

Configurar una solución que reciba y envíe mensajes con codificación EDIINT/AS2 a través de un transporte HTTP.    


## <a name="do-more"></a>Llevar a cabo más  
 Para obtener más información sobre arquitectura y conceptos de BizTalk Server, tenga en cuenta lo siguiente:  
  
[Introducción](../core/getting-started-with-biztalk-server.md)
  
[Planear y diseñar la solución de BizTalk Server](../core/plan-and-architect-your-biztalk-server-solution.md)