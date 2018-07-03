---
title: Adaptador de recepción HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a21679c2000f85d8fa4ae32f4959b79bd8c55f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977061"
---
# <a name="http-receive-adapter"></a>Adaptador de recepción HTTP
La ubicación de recepción del adaptador de recepción HTTP es una dirección URL distinta configurada a través de la consola de administración de BizTalk Server.  
  
 Puede configurar el adaptador de recepción HTTP para el envío asincrónico o sincrónico desde el cliente. Los envíos asincrónicos unidireccionales, mientras que los envíos sincrónicos son bidireccionales o envíos de solicitud-respuesta.  
  
 Utilice la seguridad de IIS para la autenticación y autorización de solicitudes entrantes.  
  
## <a name="http-get-and-http-post-requests"></a>Solicitudes HTTP GET y HTTP POST  
 La recepción HTTP de adaptador puede recibir mensajes de dos maneras diferentes: mediante una solicitud HTTP POST o una solicitud HTTP GET.  
  
 Cuando un adaptador de recepción HTTP obtiene mensajes con una solicitud HTTP POST, se produce esta secuencia de sucesos:  
  
1. La dirección URL configurada en BizTalk Server recibe un mensaje nuevo en la ubicación de recepción.  
  
2. El adaptador de recepción crea un objeto de mensaje de BizTalk para poder enviar el mensaje al servidor.  
  
3. El adaptador de recepción crea el objeto de mensaje de BizTalk con solo una parte, la parte del cuerpo.  
  
4. Una vez que se ha leído el mensaje y se ha enviado correctamente al servidor, el adaptador de recepción HTTP envía un código HTTP 202 al cliente para indicar que se aceptó la solicitud.  
  
    Opcionalmente, el adaptador de recepción HTTP puede enviar un token de correlación de mensaje en la respuesta HTTP. Este token de correlación representa el mensaje en BizTalk Server. Si la ubicación de recepción HTTP se encuentra en un puerto de solicitud-respuesta, el adaptador devuelve el código de recepción correcta 200 junto con el mensaje de respuesta.  
  
   Cuando un adaptador de recepción HTTP procesa mensajes de una solicitud HTTP GET, el adaptador de recepción crea un objeto de mensaje de BizTalk y pone la cadena de consulta descodificada de la solicitud HTTP GET en la parte del cuerpo del mensaje de BizTalk. El adaptador de HTTP selecciona la cadena de consulta que se pone en la parte del cuerpo del mensaje de BizTalk con el siguiente algoritmo:  
  
-   Si el adaptador de recepción HTTP recibe una solicitud HTTP GET, divide la cadena de URI entrante en dos partes, utilizando el signo de interrogación (?) como delimitador.  
  
-   La primera parte de la cadena URI, la parte antes del delimitador de signo de interrogación, se copia en el **InboundTransportLocation** propiedad en el contexto del mensaje. El **InboundTransportLocation** propiedad identifica la ubicación donde BizTalk Server recibió el mensaje. El motor utiliza esta propiedad para determinar la ubicación de recepción que se debe ejecutar para el mensaje.  
  
-   El adaptador de HTTP toma el resto de la cadena de URI (después del signo de interrogación) y la descodifica y copia en la parte del cuerpo del mensaje de BizTalk.  
  
-   Si el adaptador de recepción HTTP recibe una operación HTTP GET o HTTP POST vacía, se rechaza.  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a>Cómo procesa el adaptador de recepción HTTP una solicitud GET  
 A continuación se muestran algunos ejemplos de cómo procesa el adaptador de recepción HTTP los mensajes recibidos con solicitudes HTTP GET. Estos mensajes asumen que el adaptador de recepción HTTP está configurado con las siguientes ubicaciones de recepción:  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  Dada la siguiente solicitud HTTP GET para el cliente:  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     El adaptador de recepción HTTP actúa del siguiente modo:  
  
     Establecer el **InboundTransportLocation** propiedad en el contexto del mensaje igual a /vroot/BTSHTTPReceive.dll y la parte de cuerpo del objeto de mensaje de BizTalk igual a LocationID = 1.  
  
2.  Dada la siguiente solicitud HTTP GET para el cliente:  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     El adaptador de recepción HTTP actúa del siguiente modo:  
  
     Establecer el **InboundTransportLocation** propiedad igual a /vroot/BTSHTTPReceive.dll y el cuerpo del objeto de mensaje de BizTalk parte igual a LocationID = 1 & MyParam = My Value.  
  
3.  Dada la siguiente solicitud HTTP GET para el cliente:  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     Adaptador de recepción de la acción realizada por HTTP es + como sigue:  
  
     Rechace la solicitud debido al formato incorrecto de la solicitud HTTP GET.  
  
## <a name="batching-support-for-the-http-receive-adapter"></a>Compatibilidad del adaptador de recepción HTTP con el procesamiento por lotes  
 El adaptador de recepción HTTP envía mensajes al servidor en lotes. El tamaño del lote utilizado para enviar mensajes al servidor se puede configurar en el controlador de recepción del adaptador de HTTP.  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a>Capacidad del adaptador de recepción HTTP para suspender solicitudes con errores  
 El adaptador de recepción HTTP de BizTalk Server tiene un valor de configuración, **suspender solicitudes con errores**, para controlar lo que ocurre con una solicitud HTTP si se produce un error de procesamiento entrante debido a un error de canalización de recepción, un error de asignación, o un Error de enrutamiento. Esta opción de configuración tiene dos valores posibles:  
  
-   **Es False.** Esta es la configuración predeterminada. El adaptador de recepción HTTP descarta los mensajes que dan error en el procesamiento de entrada debido a un error de canalización de recepción, un error de asignación o un error de enrutamiento. Además, se envía un código de estado de error 401 o 500 al cliente. 
  
-   **Es true.** El adaptador de recepción HTTP suspende los mensajes que dan error en el procesamiento de entrada debido a un error de canalización de recepción, un error de asignación o un error de enrutamiento. Para unidireccional puertos de recepción un **aceptado** se envía el código de estado 202 al cliente. Para bidireccional puertos de recepción un **Error** código de estado 500 se envía al cliente.  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a>Compatibilidad del adaptador de recepción HTTP con la codificación fragmentada  
 El adaptador de recepción HTTP acepta solicitudes HTTP con mensajes que tienen el cuerpo con codificación fragmentada. El adaptador de recepción utiliza la codificación fragmentada para enviar mensajes de respuesta cuando el tamaño del cuerpo es superior a 4 KB. La codificación fragmentada se puede desactivar estableciendo la clave del Registro DWORD se describe en [parámetros de ajuste y configuración del adaptador de HTTP](../core/http-adapter-configuration-and-tuning-parameters.md)  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a>Certificados de cliente para el adaptador de recepción HTTP  
 Siempre que se utiliza una conexión segura con un certificado de cliente para la ubicación de recepción HTTP, el adaptador de recepción HTTP obtiene la huella digital del certificado de cliente de Microsoft Internet Information Services (IIS) y la agrega al contexto de todos los mensajes que se recibieron mediante HTTPS en esa ubicación. El adaptador de recepción HTTP establece las siguientes propiedades del sistema:  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a>Códigos de estado devueltos por el adaptador de recepción HTTP  
 La lista siguiente contiene los códigos de estado devueltos por el adaptador de recepción HTTP.  
  
-   **200 ACEPTAR.** El adaptador procesó correctamente el mensaje de solicitud y generó una respuesta. El adaptador devuelve este código de estado en la respuesta HTTP del puerto de solicitud-respuesta HTTP.  
  
-   **Mensaje 202 aceptado.** El adaptador envió correctamente el mensaje al servidor o una solicitud unidireccional está suspendida. El adaptador devuelve este código de estado en la respuesta HTTP del puerto de recepción HTTP unidireccional.  
  
-   **401 Acceso denegado.** La solicitud HTTP se recibe en un puerto de recepción que requiere autenticación y la comprobación de seguridad de ese mensaje da error. Por ejemplo, no se resolvió la entidad o no se descifró el mensaje.  
  
-   **Error de servidor interno 500.** Error general al procesar la solicitud HTTP. No se suspende el mensaje de BizTalk Server a menos que la opción de configuración **suspender solicitudes con errores** está establecido en **True** puerto de recepción para los dos sentidos.  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de HTTP](../core/http-adapter.md)