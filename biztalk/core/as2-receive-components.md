---
title: AS2 Componentes de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c919a54a307a234237dd4086a0abf2a2c0c2fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232556"
---
# <a name="as2-receive-components"></a>Componentes de recepción de AS2
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa varios componentes para recibir mensajes AS2.  
  
## <a name="as2-receive-pipelines"></a>Canalizaciones de recepción AS2  
 La mayor parte del procesamiento de recepción de AS2 se realiza en las siguientes canalizaciones de recepción de AS2. Estas canalizaciones se instalan en `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` en \Program componentes de BizTalk Server 20xx\Pipeline\\.  
  
 **Canalización AS2EdiReceive**  
  
 Esta canalización procesa los mensajes EDI recibidos a través de AS2, que incluye los MDN. La canalización consta de los siguientes componentes de canalización:  
  
-   Descodificador AS2  
  
-   Desensamblador EDI  
  
-   BatchMarker.  
  
    > [!NOTE]
    >  Cuando se utiliza la canalización AS2EdiReceive, debe agregar la cuenta de usuario que el proceso de instancia de host aislado de BizTalk esté ejecutando en el grupo de usuarios de la aplicación de BizTalk. La canalización AS2EdiReceive se ejecuta en el proceso de instancia de host aislado de BizTalk. La canalización AS2EdiReceive obtiene acceso al almacén de SSO, que requiere que el usuario se encuentre en el grupo de usuarios de la aplicación de BizTalk.  
  
 **Canalización AS2Receive**  
  
 Esta canalización procesa los mensajes recibidos a través de AS2 cuando los mensajes no están codificados en EDI. Estos mensajes se tratan como mensajes binarios. La canalización también procesa los MDN recibidos a través de AS2. La canalización consta de los siguientes componentes de canalización:  
  
-   Descodificador AS2  
  
-   Desensamblador AS2  
  
## <a name="as2-receive-pipeline-components"></a>Componentes de la canalización de recepción AS2  
 Las canalizaciones de recepción AS2 usan los siguientes componentes de canalización. Estos componentes se instalan en `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` en \Program componentes de BizTalk Server 20xx\Pipeline\\.  
  
> [!NOTE]
>  La canalización de recepción AS2 solo se admite en un proceso de Host de BizTalk de 32 bits.  
  
 **Descodificador de AS2**  
  
 El Descodificador AS2 se incluye en la fase de descodificación de las canalizaciones de recepción AS2EDIReceivePipeline y AS2Receive. Usa el componente de canalización S/MIME de BizTalk para proporcionar la funcionalidad de descodificación S/MIME a mensajes AS2 y MDN.  
  
-   Procesa encabezados AS2/HTTP.  
  
-   Comprueba la firma en caso de que el mensaje estuviera firmado.  
  
-   Descifra los mensajes si estaban cifrados (para un mensaje EDI/AS2, no un MDN).  
  
-   Descomprime el mensaje si estaba comprimido.  
  
-   Reconcilia un MDN recibido con el mensaje de salida original.  
  
-   Actualiza y correlaciona registros en la base de datos sin repudio.  
  
-   Escribe registros para los informes de estado de AS2.  
  
    > [!NOTE]
    >  Si se produce un error durante el procesamiento de la recepción de un mensaje AS2, el descodificador AS2 detendrá el procesamiento inferior de los mensajes (por ejemplo, el desensamblador EDI no analizará el intercambio). Sin embargo, el desensamblador AS2 o el desensamblador EDI seguirán generando el MDN.  
  
    > [!NOTE]
    >  En mensajes AS2, se usa la codificación de 8 bits. La codificación Base64 solo se aplica a firmas en mensajes AS2 y MDN.  
  
 **Desensamblador AS2**  
  
 En la canalización de recepción AS2Receive, el desensamblador AS2 lleva a cabo lo siguiente:  
  
-   Determina si es necesario un MDN y si este debe ser sincrónico o asíncrono.  
  
-   Genera un MDN AS2.  
  
-   Si el MDN es sincrónico, establece la propiedad `EdiIntAS.IsAS2AsynchronousMDN` como False; si es asíncrono, establece la propiedad Async como True.  
  
-   Establece las propiedades y los tokens de correlación en el MDN.  
  
 **Desensamblador EDI**  
  
 En AS2EDIReceivePipeline, el desensamblador EDI analizará el mensaje EDI en mensajes XML intermedios para su procesamiento. Para obtener más información, consulte [cómo funciona el de desensamblador de EDI](../core/how-the-edi-disassembler-works.md).  
  
 **BatchMarker**  
  
 En AS2EDIReceivePipeline, el componente de canalización BatchMarker establece las propiedades de contexto AgreementPartIdForSend y ToBeBatched que son necesarias para el procesamiento de un intercambio por lotes. Este componente se incluye en la última fase (resolución de acuerdos) de la canalización AS2EDIReceive. Todas las canalizaciones que vayan a procesar por lotes los mensajes EDI deben incluir el componente de canalización BatchMarker.  
  
> [!NOTE]
>  El componente de canalización BatchMarker no se incluye en la canalización AS2Receive usada para procesar mensajes que no son EDI. Sin embargo, puede incluir el componente BatchMarker en una canalización de recepción personalizada que no incluya el desensamblador EDI. Para obtener más información, vea "Procesamiento de EDI no mensajes en el componente de BatchMarker" en [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).  
  
## <a name="http-adapter"></a>Adaptador de HTTP  
 Los puertos y las ubicaciones de recepción usadas para el procesamiento de AS2 usan el adaptador de HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de HTTP está configurado para la transmisión unidireccional y de solicitud-respuesta.  
  
## <a name="non-repudiation-database"></a>Base de datos sin repudio  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la base de datos sin repudio (la tabla EdiMessageContent de la base de datos BizTalkDTADb) para realizar lo siguiente:  
  
> [!NOTE]
>  La tabla EdiMessageContent se encuentra en la base de datos BizTalkDTADb solo si una de las propiedades de acuerdo de almacenamiento sin repudio está activada.  
  
-   Proporciona una pista sin repudio para el MDN firmado.  
  
-   Correlaciona un mensaje de salida con su MDN entrante.  
  
-   Almacena mensajes a través de varios cambios de estado.  
  
-   Asocia códigos de error con respuesta HTTP y MDN.  
  
-   Muestra registros en función de los criterios de filtro.  
  
-   Archiva registros marcados.  
  
> [!IMPORTANT]
>  Para asegurarse de la autenticación e integridad de los mensajes almacenados en la base de datos de recepción sin repudio, deben usarse firmas digitales en todos los mensajes que se van a almacenar en la base de datos, tanto los MDN como los mensajes AS2 originales. Para obtener más información, vea la sección 9.1 de [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)