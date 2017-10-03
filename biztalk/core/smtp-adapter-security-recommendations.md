---
title: Recomendaciones de seguridad del adaptador de SMTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca1aeed0ad8c80cc32d333aeef37d1da6feabfc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-security-recommendations"></a>Recomendaciones de seguridad del adaptador de SMTP
El adaptador de SMTP se utiliza para intercambiar información entre un servidor que ejecuta Microsoft BizTalk Server y otras aplicaciones a través del Protocolo simple de transferencia de correo (SMTP). BizTalk Server puede enviar mensajes a otras aplicaciones mediante la creación de un mensaje de correo electrónico y su entrega a una dirección de correo electrónico especificada. El adaptador de SMTP sólo puede utilizarse para enviar mensajes. Para obtener más información acerca del adaptador de SMTP, consulte [adaptador de SMTP](../core/smtp-adapter.md).  
  
 Cuando configure la cuenta de servicio para la instancia de host que ejecuta el adaptador de SMTP, deberá especificar el tipo de autenticación que desea utilizar con el servidor SMTP remoto. Las opciones de autenticación son las siguientes: autenticación básica (texto sin cifrar), autenticación NTLM (utiliza las credenciales actuales) o ninguna autenticación (si la autenticación no es necesaria para el servidor SMTP).  
  
 Cuando se envía un mensaje utilizando el adaptador de SMTP, BizTalk Server envía el mensaje en texto sin cifrar de forma predeterminada. Si utiliza una canalización que tenga un componente de codificador S/MIME, podrá cifrar el mensaje antes de enviarlo al servidor SMTP. Sin embargo, el encabezado SMTP permanecerá como texto sin cifrar.  
  
 Si desea auditar los mensajes de correo electrónico que envía BizTalk Server, deberá utilizar el adaptador de SMTP para establecer una conexión con su propio servidor SMTP, dónde podrá entonces auditar los mensajes.  
  
 El adaptador de SMTP no admite Capa de sockets seguros (SSL).  
  
## <a name="see-also"></a>Vea también  
 [Puertos para los servidores de envío y recepción](../core/ports-for-the-receive-and-send-servers.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)