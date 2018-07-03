---
title: AS2 Componentes de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3378dbb623c2d47a56946805908f9d104500a8ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994565"
---
# <a name="as2-send-components"></a>Componentes de envío de AS2
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza varios componentes para enviar mensajes AS2.  
  
## <a name="as2-send-pipelines"></a>Canalizaciones de envío de AS2  
 La mayor parte del procesamiento de envío de AS2 se realiza en las siguientes canalizaciones de envío de AS2. Estas canalizaciones se instalan en `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` en \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components.  
  
> [!NOTE]
>  La canalización de envío de AS2 solo se admite en un proceso de Host de BizTalk de 32 bits.  
  
 **Canalización AS2EDISend**  
  
 Esta canalización genera y envía los mensajes EDI a través de AS2. La canalización consta de los siguientes componentes de canalización:  
  
- Ensamblador EDI  
  
- Codificador AS2  
  
  Esta canalización no se usa para generar y enviar MDN a través de AS2, ya que el MDN no necesita que el ensamblador EDI lo procese. Use la canalización AS2Send para enviar MDN.  
  
> [!NOTE]
>  La ejecución de la canalización AS2EDISend desde una orquestación no está admitida.  
  
 **Canalización AS2Send**  
  
 Esta canalización envía mensajes a través de AS2 cuando los mensajes no están codificados en EDI. También envía MDN a través de AS2. La canalización consta de los siguientes componentes de canalización:  
  
- Codificador AS2.  
  
  Si los mensajes que van a enviarse a través de AS2 no son mensajes EDI ni XML, puede crear una canalización AS2Send personalizada para controlar estos mensajes. Esta canalización debe tener un ensamblador personalizado para convertir el XML intermedio de BizTalk Server a otro formato antes de codificar el mensaje en EDIINT/AS2.  
  
> [!NOTE]
>  La ejecución de la canalización AS2Send desde una orquestación no está admitida.  
  
## <a name="as2-send-pipeline-components"></a>Componentes de la canalización de envío de AS2  
 Las canalizaciones de envío de AS2 usan los siguientes componentes de canalización. Estos componentes se instalan en `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` en BizTalk Server 20xx\Pipeline Components \Program Files\Microsoft\\.  
  
 **Ensamblador EDI**  
  
 En las canalizaciones de envío de EDIINT, el ensamblador EDI serializa el intercambio EDI.  
  
 **Codificador AS2**  
  
 El codificador AS2 se incluye en la fase de codificación de las canalizaciones de envío AS2. Usa el componente de canalización S/MIME de BizTalk para proporcionar la funcionalidad de codificación S/MIME a mensajes AS2 y MDN. El codificador AS2 realiza las operaciones siguientes:  
  
-   Aplica encabezados AS2/HTTP.  
  
-   Firma mensajes salientes, si esta opción está habilitada.  
  
-   Cifra mensajes salientes, si esta opción está habilitada (para EDI/AS2, no MDN).  
  
-   Comprime el mensaje saliente, si esta opción está habilitada (para EDI/AS2, no MDN).  
  
-   Almacena la carga en su formato correspondiente si la **NRR habilitado para mensajes AS2 salientes descodificados** propiedad está seleccionada y almacena el mensaje en su formato correspondiente si la **NRR habilitado para mensajes AS2 codificados de salida** Seleccionar propiedad  
  
-   Calcula el valor MIC y lo guarda en el almacén de datos  
  
-   Actualiza y correlaciona registros en la base de datos de recepción sin repudio.  
  
-   Para mensajes MDN, funciona igual que una canalización de paso a través: enruta el MDN generado por el descodificador AS2 en la canalización de recepción AS2Receive. Si la configuración lo requiere, el codificador AS2 firmará el MDN.  
  
    > [!NOTE]
    >  En mensajes AS2, se usa la codificación de 8 bits. La codificación Base64 solo se aplica a firmas en mensajes AS2 y MDN.  
  
## <a name="http-adapter"></a>Adaptador de HTTP  
 Los puertos de envío utilizados para el procesamiento de EDIINT AS2 utilizan el adaptador de HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de HTTP está configurado en la transmisión de petición-respuesta y en la unidireccional.  
  
## <a name="non-repudiation-database"></a>Base de datos sin repudio  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la base de datos sin repudio (la tabla EdiMessageContent de la base de datos BizTalkDTADb) para realizar lo siguiente:  
  
> [!NOTE]
>  La tabla EdiMessageContent existe en la base de datos BizTalkDTADb solo si una de las propiedades del acuerdo de almacenamiento sin repudio está activada.  
  
-   Proporcionar una pista sin repudio para el MDN firmado.  
  
-   Correlacionar un mensaje de salida con su MDN entrante.  
  
-   Almacenar mensajes a través de varios cambios de estado.  
  
-   Asociar códigos de error con respuesta HTTP y MDN.  
  
-   Mostrar registros en función de los criterios de filtro.  
  
-   Archivar registros marcados.  
  
> [!IMPORTANT]
>  Para asegurarse de la autenticación e integridad de los mensajes almacenados en la base de datos sin repudio, pueden usarse firmas digitales en todos los mensajes que se van a almacenar en la base de datos, tanto los MDN como los mensajes AS2 originales. Para obtener más información, vea la sección 9.1 de [RFC 1430, "MIME-Based segura Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).  
  
## <a name="see-also"></a>Vea también  
 [Cómo envía BizTalk Server los mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)