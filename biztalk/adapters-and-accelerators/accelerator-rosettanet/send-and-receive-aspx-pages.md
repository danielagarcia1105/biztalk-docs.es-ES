---
title: Enviar y recibir páginas ASPX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, ASPX pages
- ASPX pages, initiator
- HTTP adapters
- connections, HTTP adapters
- connections, single-action
- ASPX pages, responder
- single-action connections
- RNIFSend.aspx
- connections, asynchronous
- ASPX pages, about ASPX pages
- double-action connections
- connections, synchronous
- connections, double-action
- ASPX pages
- HTTP adapters, connections
- asynchronous connections
- RNIFReceive.aspx
- synchronous connections
ms.assetid: 21e52390-35d8-44b1-a5cd-1cd60cfe6e61
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e688686e8bd787e22d7e5a246e0cce62f469649c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982053"
---
# <a name="send-and-receive-aspx-pages"></a>Enviar y recibir páginas ASPX
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] páginas ASPX son las interfaces directas entre [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] e Internet. Las dos páginas ASPX son la página de recepción (RNIFReceive.aspx) y la página de envío (RNIFSend.aspx). Cada página ASPX es una extensión correspondiente [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización. La canalización requiere que la página ASPX para controlar los encabezados de RosettaNet Implementation Framework (RNIF). La canalización lleva a cabo la mayor parte del procesamiento; HTTP Sin embargo, cada página ASPX realiza el procesamiento de HTTP de los encabezados RNIF. Las páginas de aumentan su funcionalidad en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador de HTTP.  
  
 Cada página ASPX es un ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] sin interfaz de usuario de aplicación Web. Usa ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web de seguridad para garantizar una conexión segura con usuarios externos. Proporcionan una capa en el que puede implementar servicios de alta disponibilidad, escalabilidad y tolerancia a errores.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala una página RNIFSend.aspx y una página de trabajo RNIFReceive.aspx en cada implementación de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. Cuando el iniciador o el servicio de respuesta intercambia mensajes con el socio comercial, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] utiliza las páginas ASPX para enviar mensajes a o recibir mensajes de la dirección URL de socio. Si usan el iniciador y el Respondedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], las dos páginas ASPX en el iniciador intercambian mensajes con las dos páginas ASPX en el servicio de respuesta. Para obtener más información, consulte el "cómo iniciador y Respondedor ASPX páginas interactúan" subsección siguiente.  
  
## <a name="send-aspx-page"></a>Enviar página ASPX  
 La página RNIFSend.aspx recibe un mensaje desde el adaptador de HTTP de BizTalk. Crea y agrega los encabezados RNIF al mensaje y, a continuación, envía el mensaje al socio comercial a través de Internet. El adaptador de HTTP llama RNIFSend.aspx con el siguiente comando:  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 La cadena de consulta incluye los siguientes datos que necesita la página de envío para enviar el mensaje al socio comercial y los datos que el asociado debe tener para procesar el mensaje:  
  
- La dirección URL de socio comercial: http://www.\< *dirección*\>.com/RNIFReceive.aspx  
  
- El tipo de respuesta: sincrónica o asincrónica  
  
- La versión RNIF: 1.1 o 2.0.  
  
  El adaptador de HTTP de BizTalk envía un mensaje MIME generado por el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización de envío a la página del RNIFSend.aspx del iniciador. RNIFSend.aspx procesa el mensaje siguiente:  
  
1.  La página de envío realiza la validación en el mensaje.  
  
2.  La página de envío crea un encabezado de extensiones multipropósito de correo Internet (MIME) según el tipo de contenido, la longitud, el identificador y la versión MIME. El encabezado MIME y límites MIME superiores e inferiores, lo agrega al mensaje.  
  
3.  Para RNIF 2.01, la página de envío establece las propiedades del encabezado HTTP de la siguiente manera:  
  
    1.  Establece la propiedad X-RN-Version a la versión especificada en la propiedad de versión de la configuración del proceso.  
  
    2.  Establece la propiedad X-RN-ResponseType en sync o async, dependiendo del valor de la propiedad IsSynchronous en las opciones de configuración de proceso.  
  
    3.  Establece la propiedad Content-Length en el tamaño del mensaje completo.  
  
4.  Mediante una solicitud HTTP Post, la página de envío envía el mensaje a la dirección URL de destino del asociado, como se establece en la configuración de dirección URL de acción o señal en el acuerdo entre socios comerciales.  
  
5.  La página de envío espera a que la respuesta HTTP. Cuando recibe la respuesta, lo enruta al adaptador de HTTP.  
  
6.  Si la conexión es asincrónica, la página de envío cierra la conexión y su procesamiento está completo.  
  
7.  Si la conexión es sincrónica, la página de envío mantiene la conexión abierta para un mensaje devuelto. Después de recibir el mensaje, realiza el mismo proceso que una página de trabajo RNIFReceive.aspx realiza en un mensaje recibido, envía el mensaje recibido al adaptador de HTTP y, a continuación, cierra la conexión.  
  
## <a name="receive-aspx-page"></a>Aparece la página ASPX  
 La página de trabajo RNIFReceive.aspx recibe un mensaje HTTP del socio a través de Internet. Procesa, se valida y, a continuación, quita los encabezados RNIF y envía el mensaje al adaptador de HTTP. El mensaje recibido por la página de recepción debe ser compatible con el transporte HTTP de RNIF. La página de recepción procesa los mensajes como sigue:  
  
1.  La página de trabajo RNIFReceive.aspx Respondedor recibe el mensaje del iniciador. El mensaje contiene el encabezado MIME y los límites superiores e inferiores.  
  
2.  La página de recepción valida el encabezado MIME.  
  
3.  La página de recepción quita el encabezado MIME y los límites del mensaje.  
  
4.  La página de recepción envía el mensaje al adaptador de HTTP con la ubicación de recepción HTTP. La página de recepción recibe una respuesta HTTP y devuelve la respuesta HTTP a la página de envío del iniciador.  
  
5.  Si la conexión es asincrónica, cierra la conexión en la página de recepción.  
  
6.  Si la conexión es sincrónica, la página de recepción mantiene la conexión abierta, esperando un mensaje devuelto.  
  
7.  Después de recibir el mensaje devuelto desde el adaptador de HTTP, la página recibir el mismo procesamiento que realiza una página RNIFSend.aspx realiza y envía el mensaje devuelto a la página de envío de iniciador. Después de recibir la respuesta HTTP, cierra la conexión.  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a>Cómo interactúan las páginas ASPX iniciador y Respondedor  
 Si usan el iniciador y el Respondedor [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], las cuatro páginas ASPX en el iniciador y Respondedor interactúan de forma diferente dependiendo de si las conexiones son sincrónicas o asincrónicas, y si los mensajes son acción única o de doble acción . Las siguientes subsecciones describen el conjunto completo de las interacciones.  
  
 **Doble acción asincrónica**  
  
 Este escenario implica cuatro conexiones HTTP independientes, uno para cada paso:  
  
1. Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.  
  
   > [!NOTE]
   >  Los pasos 2 y 3 siguiente pueden producirse en el orden inverso, dependiendo de la carga del sistema.  
  
2. Página de recepción de los envíos de página de servicio de respuesta enviar una señal de solicitud de mensajes al iniciador.  
  
3. Los envíos de página Respondedor enviar una respuesta de acción del mensaje para el iniciador reciben la página.  
  
4. Página de recepción de los envíos de página iniciador enviar una señal de respuesta de mensaje para el servicio de respuesta.  
  
   **Acción única asincrónica**  
  
   Este escenario implica dos conexiones HTTP independientes, uno para cada paso. Tenga en cuenta que este escenario consta de los pasos 1 y 2 del escenario de doble acción asincrónico.  
  
5. Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.  
  
6. Página de recepción de los envíos de página de servicio de respuesta enviar una señal de solicitud de mensajes al iniciador.  
  
   **Doble acción sincrónica**  
  
   Este escenario implica una conexión HTTP:  
  
7. Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.  
  
8. El Respondedor recibe página envía un mensaje de respuesta de acción (o una excepción, si hay un problema) a la página de envío de iniciador en la misma conexión que utilizó en el paso 1.  
  
   **Acción única sincrónica**  
  
   Este escenario implica una conexión HTTP:  
  
9. Página de recepción de los envíos de página iniciador enviar la solicitud de acción del mensaje para el servicio de respuesta.  
  
10. El Respondedor recibe página envía un mensaje de señal de solicitud (o una excepción, si hay un problema) a la página de envío de iniciador en la misma conexión.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)   
 [Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [Canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)