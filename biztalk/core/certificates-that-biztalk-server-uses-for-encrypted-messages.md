---
title: Certificados que utiliza BizTalk Server para mensajes cifran | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f2dbd51506da7b505f66b3001b8bdc6fa0a58ac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a>Certificados que BizTalk Server usa para los mensajes cifrados
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite mediante clave pública el cifrado de mensajes salientes y el descifrado de mensajes entrantes según las extensiones seguras multipropósito de correo Internet (S/MIME). BizTalk Server utiliza S/MIME versión 3 para el cifrado de mensajes salientes, y S/MIME versiones 2 y 3 para el descifrado de mensajes entrantes.  
  
-   BizTalk Server admite certificados de cifrado RSA y Diffie Hellman.  
  
-   BizTalk Server admite los algoritmos de cifrado Estándar de cifrado de datos (DES), 3DES y RC2.  
  
 La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server recibe un mensaje cifrado.  
  
 ![Flujo de mensajes al recibir un mensaje cifrado](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")  
  
 El flujo de mensajes generado cuando BizTalk Server recibe un mensaje cifrado es como sigue:  
  
1.  Un socio envía un mensaje a BizTalk Server. El socio cifra el mensaje con la clave pública de BizTalk Server.  
  
2.  El mensaje es recibido por el controlador de recepción correspondiente de BizTalk Server.  
  
3.  Durante la ejecución de la canalización de recepción, el componente de canalización Descodificador de MIME/SMIME descifra el mensaje mediante la clave privada de BizTalk Server.  
  
    > [!NOTE]
    >  Para que el descifrado de canalización se complete correctamente en un equipo con IIS 7.0, asegúrese de que la cuenta para el grupo de aplicaciones de IIS y la cuenta utilizada por la instancia de host asociada con el controlador de recepción son los mismos y que esta cuenta es miembro de la \<machineName \>Grupo \IIS_WPG. Para obtener más información acerca de cómo configurar IIS procesar identidad para IIS 7.0, vea [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md). Estos procesos se deben ejecutar en la misma cuenta para comprobar que se carga el perfil de cuenta que, a su vez, carga las claves de registro necesarias para llevar a cabo el descifrado en la canalización. Por motivos de rendimiento, IIS 7.0 no carga el perfil de cuenta al iniciar el proceso w3wp.exe asociado, de modo que la instancia de host de BizTalk debe configurarse con la misma cuenta, para que BizTalk cargue el perfil de cuenta y las claves del Registro.  
  
4.  Se produce un procesamiento adicional.  
  
 La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server envía un mensaje cifrado.  
  
 ![Flujo de mensajes al enviar un mensaje cifrado](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")  
  
 La siguiente ilustración muestra el flujo de mensajes generado cuando BizTalk Server envía un mensaje cifrado a un socio:  
  
1.  El mensaje es enviado al socio por el controlador de envío correspondiente de BizTalk Server.  
  
2.  Durante la ejecución de la canalización de envío, el componente de canalización Descodificador de MIME/SMIME cifra el mensaje mediante la clave pública del socio.  
  
3.  El socio recibe el mensaje de BizTalk Server. El socio utiliza su clave privada para descifrar el mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [Almacenes de certificados que utiliza BizTalk Server](../core/certificate-stores-that-biztalk-server-uses.md)   
 [Cifrado y certificados de firma](../core/encryption-and-signing-certificates.md)   
 [Envío y recepción de mensajes cifrados](../core/sending-and-receiving-encrypted-messages.md)