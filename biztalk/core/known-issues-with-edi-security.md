---
title: Problemas conocidos con la seguridad EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d7f68bc-8460-4656-b9f2-955337458d78
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9517f6c5b1aeae06b5989eef12fe269f81a27c74
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22262436"
---
# <a name="known-issues-with-edi-security"></a>Problemas conocidos de la seguridad de EDI
En este tema se describen problemas conocidos relacionados con la seguridad de las soluciones EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a>BizTalk no suspenderá un mensaje firmado de una entidad para la que no se ha establecido ningún certificado  
 Si no establece ningún certificado de firma en una entidad (en el nodo Certificado de la página Propiedades de entidades de la entidad), pero se firma un mensaje entrante de esa entidad, BizTalk Server no suspenderá el mensaje y lanzará una excepción basada en la ausencia de certificado.  
  
 Si anula las propiedades del mensaje entrante (en la página Entidad como remitente del mensaje AS2), y borra la propiedad "Debe firmarse el mensaje", BizTalk Server suspenderá los mensajes entrantes firmados.  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a>El acceso a la carpeta Archivos de programa puede estar limitado para evitar la manipulación de archivos  
 Si la carpeta Archivos de programa que contiene los ejecutables de BizTalk Server y los esquemas de EDI está disponible para los usuarios no autenticados, esos usuarios podrían modificar esos archivos. Como medida de protección frente a esa amenaza, puede utilizar las listas de control de acceso (ACL) en la carpeta Archivos de programa para limitar el acceso a los usuarios de confianza.  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a>Un esquema con un campo largo puede ser susceptible de sufrir un ataque de denegación de servicio  
 Un esquema personalizado que tenga un campo de gran longitud podría ser utilizado por un ataque de denegación de servicio. Los esquemas que se suministran con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tienen campos de gran longitud y, por tanto, no suelen ser susceptibles de sufrir ese tipo de ataques.  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a>El procesamiento de mensajes se anulará si un número de control supera su longitud máxima  
 Un número de control del conjunto de transacciones, intercambio o grupo tiene una longitud máxima limitada. Si la longitud de uno de estos números de control supera la longitud máxima, se anulará el procesamiento de todos los mensajes de ese tipo de codificación para una única entidad. Los mensajes con otro tipo de codificación (EDIFACT en lugar de X12, por ejemplo) no se verán afectados. Esto podría representar una vulnerabilidad de seguridad.  
  
 Si la longitud de un número de secuencia supera la longitud máxima, el usuario tiene que restablecer el número de la secuencia en la propiedad EDI de la entidad afectada. Una vez restablecida la secuencia, todos los mensajes de ese tipo de codificación pueden procesarse una vez más.  
  
 Para los mensajes X12, la longitud máxima de un número de control es de nueve dígitos. Para los mensajes EDIFACT, la longitud máxima de un número de control es 14 dígitos en tres campos.  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a>El uso de la canalización de recepción de EDI con un adaptador HTTP dejará la conexión abierta si no se envía ninguna confirmación  
 Puede producirse un problema de seguridad si crea una ubicación de recepción que utilice la canalización EDIReceive y tenga un tipo de transporte HTTP. La canalización EdiReceive no generará una confirmación HTTP “200 OK”. Si no se devuelve una confirmación EDI, la conexión no se terminará correctamente pero permanecerá abierta. La conexión agotará el tiempo cuando el período de tiempo de espera se haya agotado.  
  
 No se trata de ningún problema relacionado con la canalización AS2EdiREceive.  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>Un mensaje con codificación X12 se suspende si la autenticación basada en puerto está habilitada y BizTalk Server no dispone de acceso a la información de autorización y seguridad.  
 **Síntoma**  
  
 Cuando se recibe un mensaje a través de un puerto de recepción para el que está habilitada la autenticación y la entidad que ha enviado el mensaje no puede determinarse, BizTalk Server suspenderá el mensaje.  
  
 **Causa posible**  
  
 Si la autenticación está habilitada para un puerto de recepción (la propiedad "Sin autenticación" del puerto de recepción está desactivada), BizTalk Server necesita la configuración de las propiedades "Calificador de autorización (ISA1) e Información (ISA2)" y "Calificador de seguridad (ISA3) e Información (ISA4)" para procesar el intercambio. Estas propiedades están establecidas para una entidad en la página Propiedades de procesamiento de intercambio X12 de la entidad como remitente de intercambio. Si BizTalk Server no puede determinar los valores de estas propiedades, suspenderá el mensaje.  
  
 Esto puede ocurrir de dos maneras. En el primer caso, si BizTalk Server no puede determinar la entidad que ha enviado el mensaje, utilizará las propiedades globales de EDI y no dispondrá de acceso a la configuración de seguridad y autorización. Como resultado, suspenderá el mensaje. En el segundo caso, si BizTalk Server determina la entidad, pero las propiedades ISA1-2 e ISA3-4 de la entidad no están configuradas, BizTalk Server seguirá sin disponer de acceso a la información de seguridad y autorización y suspenderá el mensaje.  
  
 **Resolución**  
  
 Asegúrese de que la entidad de envío del mensaje puede identificarse y de que las propiedades ISA1-2 e ISA3-4 están definidas en el acuerdo de la entidad.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)