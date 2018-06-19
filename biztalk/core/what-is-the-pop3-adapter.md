---
title: ¿Qué es el adaptador de POP3? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, availability
- authenticating, POP3 adapters
- POP3 adapters, data duplication
- data duplication
- POP3 adapters, receive adapters
- high availability, POP3 adapters
- POP3 adapters, supported platforms
- POP3 adapters, authenticating
- POP3 adapters, algorithims
- receive adapters, POP3 adapters
ms.assetid: 05e9598b-cdfe-4216-b6bf-1b84f8ddfeae
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592e0475b607de3f9df528a4bab777aa0fb7635d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290628"
---
# <a name="what-is-the-pop3-adapter"></a>¿Qué es el adaptador de POP3?
Esta sección describe el adaptador de recepción POP3.  
  
## <a name="pop3-receive-adapter"></a>Adaptador de recepción POP3  
 El adaptador de recepción POP3 permite mover los datos desde un buzón habilitado para POP3 al servidor BizTalk Server.  
  
 Las principales características del adaptador de recepción POP3 son:  
  
-   Extracción de archivos del buzón del servidor POP3 a petición.  
  
-   Ejecución de sondeos basados en una programación configurable.  
  
-   Realización de sondeos del buzón del servidor POP3 y envío de datos directamente al servidor BizTalk Server.  
  
-   Especificación del buzón del servidor POP3 como dirección IP o nombre de host o dirección IP, puerto, nombre de usuario y contraseña.  
  
-   Capacidad para descargar el correo electrónico desde servidores de correo que requieren conexiones Capa de sockets seguros (SSL).  
  
-   Entrega de archivos garantizada.  
  
-   Procesamiento de MIME implícito. No resulta necesario utilizar un descodificador de MIME en una canalización de recepción al usar el adaptador de POP3.  
  
## <a name="pop3-adapter-supported-platforms"></a>Plataformas compatibles con el adaptador de POP3  
 El adaptador de POP3 está diseñado para funcionar con cualquier servidor POP3 que se ajuste a las siguientes normas RFC:  
  
-   **RFC 1939.** Post Office Protocol Version 3 (vea [http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))  
  
-   **RFC 1734.** POP3 AUTHentication command (vea [http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))  
  
-   **RFC 2045.** Multipurpose Internet Mail Extensions (MIME) Part One: Formato of Internet Message Bodies (vea [http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))  
  
-   **RFC 2046.** Multipurpose Internet Mail Extensions (MIME) parte dos: Tipos de medios (vea [http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))  
  
-   **RFC 2047.** MIME (Multipurpose Internet Mail Extensions) parte tres: Extensiones de encabezado de mensaje de texto no ASCII (vea [http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))  
  
 Se realizaron pruebas exhaustivas del adaptador de POP3 con respecto a Microsoft Exchange Server 2003.  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a>Consideraciones para evitar el duplicado de datos al utilizar el adaptador de POP3  
 El adaptador de POP3 no es un adaptador transaccional y, en consecuencia, está sujeto al procesamiento de varias copias de un mismo mensaje, lo que puede dar lugar al duplicado de datos. Es posible que el adaptador de POP3 entregue copias duplicadas de un mensaje en los siguientes casos:  
  
-   El adaptador de POP3 siempre elimina mensajes de correo electrónico del buzón para cuya supervisión está configurado tras enviar correctamente el mensaje de correo electrónico al servidor BizTalk Server para su procesamiento. Si el adaptador de POP3 recupera un mensaje de correo electrónico del buzón, lo envía al servidor BizTalk Server para su procesamiento y no logra eliminar el mensaje de correo electrónico del buzón, el mensaje se reenviará al servidor BizTalk Server la próxima vez que el adaptador de POP3 efectúe un sondeo del buzón.  
  
-   Si varias instancias del adaptador de POP3 de distintas instancias de host de BizTalk supervisan el mismo buzón de forma simultánea y el servidor POP3 permite varias conexiones concurrentes a los buzones correspondientes, el adaptador puede entregar copias duplicadas de mensajes.  
  
## <a name="high-availability-for-the-pop3-adapter"></a>Alta disponibilidad del adaptador de POP3  
 Algunos servidores POP3 permiten varias conexiones concurrentes a un buzón dado. Si más de una instancia del adaptador de POP3 está configurada para recuperar correo de un buzón de un servidor POP3 de este tipo, se pueden duplicar los datos. Por lo tanto, se debería configurar únicamente una instancia del adaptador de POP3 para recuperar el correo de un buzón que permite varias conexiones concurrentes.  
  
 Para proporcionar tolerancia a errores para el adaptador de POP3 en este caso, se debería configurar un solo controlador de recepción del adaptador de POP3 para que se ejecutase en un host de BizTalk agrupado. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a>Advertencias de autenticación cuando al conectarse varias instancias del adaptador de POP3 al mismo buzón  
 BizTalk Server puede configurarse para que más de una instancia del adaptador de POP3 recupere correo del mismo buzón. En este caso, es posible que se generen advertencias de autenticación en el registro de aplicaciones de BizTalk Server a causa del mecanismo de bloqueo que emplean algunos servidores POP3. Estas advertencias no afectarán a la funcionalidad del adaptador de POP3 y puede omitirse sin riesgos en este caso.  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a>Los mensajes cifrados que recibe el adaptador de POP3, enviados a la cola de suspensión, pueden visualizarse como texto no cifrado  
 El adaptador de POP3 puede configurarse para descifrar mensajes de correo electrónico cifrados digitalmente. Esto se hace estableciendo el **aplicar descodificación MIME** propiedad **True** para ubicaciones de recepción que utilice POP3 el adaptador. Si el adaptador de POP3 recibe un correo electrónico cifrado digitalmente y la **aplicar descodificación MIME** propiedad para la ubicación de recepción se establece en **True** , a continuación, el adaptador de POP3 intenta descifrar el correo electrónico como se indica a continuación:  
  
-   El adaptador de POP3 busca un certificado privado que coincida con el certificado público utilizado para cifrar el mensaje de correo electrónico. El certificado privado debe encontrarse en el almacén de certificados Personal del servidor que ejecuta la instancia de host a la que el controlador de recepción POP3 se encuentra enlazado.  
  
-   Si el adaptador de POP3 encuentra un certificado privado correspondiente, lo utiliza para descifrar el mensaje de correo electrónico.  
  
-   El mensaje de correo electrónico se descifra y se almacena en el cuadro de mensajes de BizTalk.  
  
 Si un mensaje se suspende después de que se descifre y se almacene en el cuadro de mensajes de BizTalk, el contenido del mensaje resultará visible como texto no cifrado en la cola de suspensión de BizTalk.  
  
 Si es preciso evitar la visualización del texto de un mensaje seguro en la cola de suspensión, siga los pasos que se indican a continuación:  
  
-   Establecer el **aplicar descodificación MIME** propiedad **False** para dicho adaptador de POP3 de uso de ubicaciones de recepción y descifrar el mensaje en una canalización con el componente de canalización SMIME.  
  
    > [!NOTE]
    >  Con ello, se evitará la posibilidad de promover propiedades específicas de correo electrónico al contexto de mensaje.  
  
-   Si resulta necesario promocionar propiedades específicas de correo electrónico al contexto de mensaje y garantizar que los mensajes cifrados sigan cifrados al enrutarse a la cola de suspensión, lleve a cabo los pasos siguientes:  
  
    -   Active la opción para **habilitar enrutamiento para mensajes con errores** en el puerto de recepción que aloja las ubicaciones de recepción que utilizan el adaptador de POP3.  
  
    -   Cree una orquestación para efectuar una suscripción a mensajes con errores de entrega al puerto de recepción que aloja las ubicaciones de recepción que utilizan el adaptador de POP3.  
  
    -   Configure la orquestación con un puerto de envío que cifre el mensaje en una canalización mediante el componente de canalización de SMIME.  
  
    -   Configure la orquestación con una forma de suspensión para suspender la instancia de orquestación y el mensaje.  
  
    -   Genere la orquestación e impleméntela; seguidamente, enlace la orquestación implementada al puerto de recepción adecuado.  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a>Tamaño máximo de mensajes compatible con el adaptador de POP3  
 Se han efectuado pruebas con el adaptador de POP3 que permiten afirmar la compatibilidad con la recepción de mensajes de hasta 50 MB de tamaño.  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de POP3](../core/pop3-adapter.md)