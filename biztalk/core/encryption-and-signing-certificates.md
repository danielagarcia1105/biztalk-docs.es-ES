---
title: Cifrado y certificados de firma | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, security
- security, certificates
- security, messages
- certificates, encryption
- encryption certificates, messages
- messages, encryption
- messages, certificates
- security, encryption
ms.assetid: 3c3f9de5-4156-4133-8d5e-c30b142b6d61
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633484a6c5599b9323bfd7798f621b27a501ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="encryption-and-signing-certificates"></a>Cifrado y certificados de firma
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se apoya en gran medida en la seguridad que ofrecen los certificados. BizTalk Server usa certificados para el cifrado y la aplicación de firmas digitales, lo que le permite enviar y recibir datos fiables y garantizar que los datos procesados sean seguros. Tanto el cifrado como las firmas digitales utilizan un certificado de clave pública y un certificado de clave privada. En el caso del cifrado, el remitente del mensaje utiliza el certificado de clave pública del receptor para cifrar el mensaje, mientras que el receptor del mensaje (BizTalk Server) utiliza su clave privada para descifrarlo. En el caso de las firmas digitales, el remitente del mensaje utiliza un certificado de clave privada para firmar el mensaje y el receptor del mensaje (BizTalk Server) utiliza el certificado de clave pública del remitente para comprobar la firma.  
  
 BizTalk Server usa certificados de clave pública para comprobar las firmas digitales de los mensajes entrantes y para cifrar los mensajes salientes. BizTalk Server usa certificados de clave privada para descifrar los mensajes entrantes y para firmar los mensajes salientes.  
  
 El usuario configura los certificados que BizTalk Server usa en el Explorador de BizTalk y en la consola de administración de BizTalk.  
  
 Para obtener más información acerca de los certificados digitales, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).  
  
> [!NOTE]
>  Mientras procesa mensajes de Extensiones seguras multipropósito de correo Internet (S/MIME), puede hacer que el motor de BizTalk Server compruebe la lista de revocación de certificados (CRL) para garantizar que un certificado no haya caducado y que se haya trazado su fiabilidad hasta una entidad emisora de certificados raíz. Esta comprobación se realiza en el componente descodificador de MIME/SMIME mientras la canalización procesa el mensaje. Para obtener más información sobre cómo establecer **Comprobar lista de revocaciones** propiedad, vea [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Almacenes de certificados que utiliza BizTalk Server](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)