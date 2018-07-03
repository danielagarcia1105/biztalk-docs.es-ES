---
title: Los certificados que utiliza BizTalk Server para mensajes firmados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, signed messages
- messages, message flow [digital signatures]
- S/MIME messages
- signed messages
- digital signatures, message flow
- messages, certificates
ms.assetid: 0b521e11-73ef-424f-9e6a-4fb42dc263ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc45411d19bc23a2985dbd60fc68bc8de58594c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979853"
---
# <a name="certificates-that-biztalk-server-uses-for-signed-messages"></a>Certificados que BizTalk Server usa para mensajes firmados
BizTalk Server admite la firma de mensajes de salida y la comprobación de firmas de mensajes de entrada en formato de extensiones seguras multipropósito al correo de Internet (Secure Multipurpose Internet Mail Extensions, S/MIME). BizTalk Server usa S/MIME versiones 2 y 3 para firmar mensajes de salida y validar la firma de mensajes de entrada. De forma parecida, se puede configurar BizTalk Server para que firme y a continuación cifre los mensajes que envía a sus socios.  
  
- BizTalk Server admite los algoritmos de firma SHA-1 y MD5 para la comprobación de firmas digitales. BizTalk Server usa el algoritmo de firma SHA-1 para firmar mensajes de salida.  
  
- Los sistemas de intercambio de claves admitidos por BizTalk Server para claves de firma son los algoritmos Rivest-Shamir-Adleman (RSA) y el Estándar de firma digital (Digital Signature Standard, DSS). BizTalk Server no admite el sistema de intercambio Estándar de cifrado avanzado (Advanced Encryption Standard, AES) para claves de firma.  
  
- El certificado de firma admitido por BizTalk Server es x.509 versión 3.  
  
  La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server recibe un mensaje firmado digitalmente y, opcionalmente, usa la firma para resolver la identidad del socio como una entidad del entorno de BizTalk Server.  
  
  ![Flujo de mensajes al enviar un mensaje firmado](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")  
  
  Este es el flujo de mensajes generado cuando BizTalk Server recibe un mensaje firmado digitalmente:  
  
1. Un socio envía un mensaje a BizTalk Server. El socio firma el mensaje con su certificado de clave privada.  
  
2. El mensaje es recibido por el controlador de recepción correspondiente de BizTalk Server.  
  
3. Durante la ejecución de la canalización de recepción, el componente de canalización Descodificador de MIME/SMIME comprueba la firma digital mediante la clave pública del socio.  
  
4. Si el componente de resolución de entidades está configurado, se usa el certificado de clave pública del socio para identificar la entidad en el sistema de BizTalk Server durante la ejecución del componente de resolución de entidades de la canalización de recepción.  
  
5. Se produce un procesamiento adicional.  
  
   La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server envía un mensaje firmado digitalmente.  
  
   ![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")  
  
   Este es el flujo de mensajes generado cuando BizTalk Server envía un mensaje firmado digitalmente a un socio:  
  
6. El mensaje es enviado al socio por el controlador de envío correspondiente de BizTalk Server.  
  
7. Durante la ejecución de la canalización de envío el componente de canalización Descodificador de MIME/SMIME comprueba la firma digital mediante la clave pública del socio.  
  
8. El socio recibe el mensaje de BizTalk Server. El socio usa la clave pública de BizTalk Server para comprobar la firma digital.  
  
   Para comprobar la validez de los certificados asociados con los mensajes firmados de entrada, BizTalk Server valida la cadena de confianza de la entidad de certificación para el certificado en cuestión y comprueba que éste no ha expirado El proceso de validación de la cadena de confianza de la entidad de certificación conlleva recorrer dicha cadena hasta alcanzar una entidad de certificación raíz. De esta forma, se valida que el certificado usado para firmar un mensaje procede realmente de la entidad identificada. Esta validación se produce en tiempo de ejecución para cada uno de los mensajes firmados.  
  
   Además, BizTalk Server puede comprobar que la entidad de certificación no ha revocado el certificado usado para firmar o cifrar el mensaje. Para ello, debe descargar la lista de revocación de certificados (CRL) desde la entidad de certificación e instalarla mediante el Explorador de Windows. Para obtener más información sobre cómo validar un certificado, consulte [cómo configurar el componente de canalización de descodificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [Almacenes de certificados que utiliza BizTalk Server](../core/certificate-stores-that-biztalk-server-uses.md)   
 [Cifrado y certificados de firma](../core/encryption-and-signing-certificates.md)   
 [Envío y recepción de mensajes firmados](../core/sending-and-receiving-signed-messages.md)