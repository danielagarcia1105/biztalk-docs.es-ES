---
title: Problemas conocidos con procesamiento de AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64899c184f8cbe405684387b8f1c2a6230204624
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-as2-processing"></a>Problemas conocidos del procesamiento de AS2
En esta sección se incluyen temas que describen los problemas conocidos de las soluciones AS2 de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a>El procesamiento de AS2 no es compatible con equipos de 64 bits.  
 La solución AS2 de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] no es compatible con los equipos de 64 bits. El procesamiento de AS2 sólo funciona en equipos de 32 bits o cuando se ejecutan en el emulador WOW64 en equipos de 64 bits.  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a>Las canalizaciones de recepción AS2 requieren que la cuenta en la que se ejecuta el proceso de instancia de host aislado de BizTalk sea parte del grupo de usuarios de la aplicación de BizTalk.  
 Si se utiliza la canalización AS2EdiReceive o AS2Receive, debe agregar la cuenta de usuario en la que se está ejecutando el proceso de instancia de host aislado de BizTalk al grupo de usuarios de la aplicación de BizTalk. Las canalizaciones AS2EdiReceive y AS2Receive se ejecutan en el proceso de instancia de host aislado de BizTalk.  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a>Un encabezado Receipt-Delivery-Option generará un envío sincrónico de un MDN.  
 En caso de que la canalización AS2Receive reciba un mensaje con un encabezado receipt-delivery-option vacío y se haya solicitado un MDN asíncrono, la canalización ignorará la solicitud de MDN asíncrono. En su lugar, devolverá un MDN asíncrono y registrará un error en el registro de evento y en el informe de estado de AS2 (si está habilitado). Esto sucede si la propiedad "Invalidar propiedades de mensajes entrantes" no está seleccionada. Si dicha propiedad estuviese seleccionada, se reemplazaría el encabezado Receipt-Delivery-Option del mensaje con el valor de la propiedad Receip-Delivery-Option de la página Entidad como remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2.  
  
 En este caso, puesto que el encabezado receipt-delivery-option está vacío, la canalización AS2Receive no dispone de ninguna dirección a la que enviar la respuesta de MDN a través de una conexión asíncrona. Sin embargo, la canalización aún dispone de una conexión sincrónica abierta, por lo que devolverá el MDN a través de dicha conexión. Si se trata de un puerto de recepción unidireccional, BizTalk Server cerrará la conexión tras enviar el mensaje HTTP 200OK.  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a>Utilizar encabezados de línea HTTP plegada y desplegada  
 Para permitir la máxima interoperabilidad, debe utilizar encabezados de línea HTTP desplegadas para los mensajes AS2. Information Services (IIS) 7.0 admite solo los encabezados HTTP que no estén plegados. IIS 6.0 admite los encabezados plegados y desplegados. Sin embargo, no todos los sistemas admiten encabezados de más de 80 caracteres por línea; por ello, en dichos sistemas deben utilizarse líneas plegadas.  
  
 El valor predeterminado de AS2 en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] es de encabezados de línea HTTP desplegados.  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a>La resolución de entidades puede verse afectada por un nombre localizado  
 Cuando BizTalk Server lleva a cabo una resolución de entidades en un mensaje AS2 saliente, la resolución de entidades puede verse afectada por un valor localizado en los encabezados del mensaje. Si la propiedad de entidad AS2-To de la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 se establece de forma predeterminada como un nombre de entidad en inglés y el valor del encabezado AS2-To del mensaje AS2 se establece como un nombre no en inglés, no se encontrará la coincidencia.  
  
## <a name="as2-message-size-limitation"></a>Límite de tamaño del mensaje AS2  
 Los mensajes AS2 cifrados deben tener un tamaño inferior a 96 megabytes para que se puedan procesar. Este límite viene impuesto por el descodificador AS2 que forma parte de las canalizaciones AS2Receive y AS2EdiReceive.  
  
 Una manera de solucionar esta limitación de tamaño consiste en utilizar la compresión, ya que los mensajes AS2 se comprimen antes del cifrado.  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>La aplicación EDI de BizTalk no debe modificarse.  
 Los artefactos en la aplicación EDI de BizTalk no deben modificarse o eliminarse. Si se modifica esta aplicación, no será posible volver a la aplicación original quitando la configuración o volviendo a configurar las características EDI y AS2.  
  
## <a name="partner-may-reject-multipart-messages"></a>El socio puede rechazar mensajes de varias partes  
 **Síntoma**  
  
 Al enviar mensajes de varias partes que usen la canalización de envío de AS2, el socio puede rechazar el mensaje porque falta un encabezado MIME de tipo de contenido.  
  
 **Causa posible**  
  
 Tipo de contenido es un encabezado opcional que puede estar presente para cada parte del cuerpo en un mensaje de varias partes. Algunos socios requieren que este encabezado esté presente para cada parte del cuerpo y configurado en un tipo de contenido específico.  
  
> [!NOTE]
>  El cuerpo del mensaje tendrá la propiedad Tipo de contenido configurada según la canalización de envío AS2. No obstante, los datos adjuntos no tendrán el conjunto de propiedades Tipo de contenido.  
  
 **Resolución**  
  
 Si el socio requiere el valor del encabezado Tipo de contenido para cada parte del cuerpo, deberá crear un componente de canalización personalizado que defina esta propiedad y use el componente en la canalización de envío.  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a>Al recibir mensajes de varias partes, la primera parte se considera el cuerpo  
 **Síntoma**  
  
 Al recibir un mensaje AS2 de varias partes, es posible que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] identifique incorrectamente uno de los archivos adjuntos como cuerpo del mensaje.  
  
 **Causa posible**  
  
 El encabezado MIME de un mensaje relacionado o de varias partes puede contener un parámetro ‘start’ opcional que indica cuál de las partes debe tratarse como cuerpo del mensaje especificando el identificador de contenido de la parte. Si el parámetro start no está presente, la primera parte debe considerarse como el cuerpo del mensaje. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no reconoce el parámetro start si está presente y siempre tratará la primera parte como el cuerpo del mensaje.  
  
 **Resolución**  
  
 Si el socio no puede enviar el cuerpo como primera parte del mensaje relacionado o de varias partes, deberá crear un componente de canalización que identifique correctamente el cuerpo del mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)   
 [AS2 Arquitectura de la solución](../core/as2-solution-architecture.md)   
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)