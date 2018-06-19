---
title: Seguridad para enviar y recibir mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1328eb98cbf94b85cda16eda431da197c6d0126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270604"
---
# <a name="security-for-sending-and-receiving-messages"></a>Seguridad de envío y recepción de mensajes
La siguiente ilustración muestra lo que le sucede a un mensaje cuando BizTalk Server lo recibe, lo procesa y lo envía a otra aplicación o a otro socio.  
  
 ![Características de seguridad para proteger los mensajes](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
Características de seguridad utilizadas durante el período de vida de un mensaje  
  
1.  La ubicación de recepción del adaptador recibe el mensaje. Dependiendo del protocolo, el adaptador realiza una autenticación de nivel de protocolo del remitente para identificar una cuenta de usuario de Windows que represente al remitente del mensaje.  
  
2.  A continuación el adaptador pasa el mensaje a la canalización, en la que se realiza la autenticación de nivel de mensaje si ésta no se había realizado ya en el adaptador.  
  
    1.  En la fase de descodificación, la canalización descifra el mensaje y comprueba la validez de la firma con el certificado adjunto al mensaje o con el configurado en el almacén de certificados Otras personas del equipo local. Una vez que la canalización valida la firma, el componente de descodificación valida la cadena de certificados hasta una entidad emisora de certificados raíz de confianza. Si el usuario configura la canalización para descodificar mensajes S/MIME y el remitente cifró el mensaje con S/MIME, el descodificador de MIME/SMIME comprueba la firma del mensaje y utiliza el certificado para identificar al remitente. Para obtener más información sobre cómo usar los componentes de canalización de descodificador MIME/SMIME, vea [implementar seguridad de los mensajes](../core/implementing-message-security.md).  
  
    2.  En la fase de resolución de entidades, BizTalk Server utiliza la información del certificado y el Id. de seguridad del remitente (SSID) obtenido de la autenticación de nivel de protocolo para determinar si el remitente del mensaje es una entidad reconocida del sistema. El SSID del remitente es el nombre completo del usuario autenticado por el adaptador. Por ejemplo. si BizTalk Server recibe el mensaje mediante el adaptador de HTTP que utiliza autenticación de Windows, el SSID del remitente es dominio\nombre de usuario. BizTalk Server asigna un Id. de entidad (PID) al mensaje, que es el identificador de entidad de una entidad reconocida o un Id. de invitado. Para obtener más información sobre cómo usar el componente de resolución de entidades, vea [con certificados para la resolución de entidades](../core/using-certificates-for-party-resolution.md).  
  
    3.  Si configuró el puerto de recepción para exigir que el remitente se autentique como una entidad conocida del sistema y BizTalk Server no encuentra ningún PID para dicho remitente, BizTalk Server descarta o suspende el mensaje, en función de la configuración del puerto de recepción. BizTalk Server proporciona esta característica para reducir la posibilidad de ataques de denegación de servicio. Para obtener más información acerca de las opciones de autenticación para puertos de recepción, consulte [cómo configurar opciones de autenticación para un puerto de recepción](../core/how-to-configure-authentication-options-for-a-receive-port.md).  
  
3.  Una vez que ha autenticado el mensaje, la canalización lo envía a la base de datos de cuadro de mensajes.  
  
    1.  Si no ha identificado el host de cola (en el que se está ejecutando la canalización) como un host con autenticación de confianza, la base de datos de cuadro de mensajes sobrescribe el PID con el Id. de invitado y el SSID con la cuenta de servicio en la que se ejecuta la instancia de host. Para obtener más información acerca de host de confianza de autenticación, vea [de mensajes entre los procesos de autenticación](../core/authentication-of-messages-between-processes.md). Para obtener más información sobre cómo configurar el host de confianza de autenticación, vea [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).  
  
    2.  Si el host en que se está ejecutando la canalización está marcado como con autenticación de confianza, la base de datos de cuadro de mensajes confía en el PID y el SSID, y deja esa información en el contexto del mensaje para que los procesos inferiores puedan utilizarla a fin de autenticar o autorizar al remitente original del mensaje.  
  
    3.  Si BizTalk Server exige autorización de recepción, la base de datos de cuadro de mensajes comprueba que los hosts suscritos al mensaje tienen autorización para recibirlo. Para obtener más información acerca de la autorización de recepción, consulte [autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md).  
  
4.  Una vez que BizTalk Server procesa el mensaje, la canalización de salida lo cifra o firma digitalmente en la fase de codificación.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de la seguridad de mensaje](../core/implementing-message-security.md)   
 [Planear la seguridad de mensaje](../core/planning-message-security.md)