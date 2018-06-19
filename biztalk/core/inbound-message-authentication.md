---
title: Autenticación de mensajes entrantes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, authenticating
- processing, inbound messages
- messages, inbound
- processing, security
- security, messages
- inbound messages
ms.assetid: 34c06283-667d-4498-8544-dea6e87f276f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ada514c771f4e6dbf0abad3f23cab54721299d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258068"
---
# <a name="inbound-message-authentication"></a>Autenticación de mensajes entrantes
BizTalk Server puede autenticar el remitente de un mensaje (mediante la información de certificado o la seguridad integrada de Windows) para validar su identidad. La siguiente ilustración muestra las características de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que puede utilizar para autenticar mensajes entrantes.  
  
 ![Características de seguridad que autentican los mensajes entrantes](../core/media/ebiz-plan-secoverview-auth-inbound.gif "ebiz_plan_secoverview_auth_inbound")  
Características de seguridad usadas por BizTalk Server para autenticar mensajes entrantes.  
  
 Al recibir un mensaje cifrado y firmado, BizTalk Server realiza los pasos siguientes para asegurarse de que la entidad remitente es reconocida.  
  
1.  Cuando un mensaje llega a una ubicación de recepción de BizTalk Server, el controlador de recepción intenta obtener el identificador de seguridad de Windows (SSID) de remitente del proceso remitente. La ubicación de recepción pasa el SSID a niveles inferiores para admitir casos en los que el agente de escucha ya haya autenticado un mensaje firmado. Si la información de certificado de cliente puede ser obtenida (por ejemplo por el adaptador de BizTalk para Message Queue o de HTTP), la ubicación de recepción de BizTalk Server puede obtenerla y pasarla para la resolución de su entidad más adelante en la canalización de recepción. Si el controlador de recepción no puede obtener el SSID, se deja este campo en blanco.  
  
     El controlador de recepción envía el mensaje a la canalización de recepción, donde éste se descifra, se comprueba la firma digital y se realiza la resolución de entidad si la canalización tiene un componente de resolución de entidad. Si el remitente utilizó un certificado de firma en el mensaje entrante, a continuación el componente descodificador de MIME/SMIME sobrescribe cualquier información de certificado obtenida del adaptador.  
  
2.  Si el remitente cifró el mensaje, el descodificador de MIME/SMIME recupera el certificado de descifrado del almacén de certificados personales para la cuenta de servicio de la instancia de host y utiliza la clave privada para descifrar el mensaje.  
  
     Si el remitente firmó el mensaje, el descodificador de MIME/SMIME autentica la firma digital comprobando si hay signos de manipulación en el hash de carga y, a continuación, recuperando el certificado del almacén de certificados para comprobar la firma. Si la clave pública del firmante está en el mensaje, el descodificador de MIME/SMIME no recupera el certificado del almacén de certificados; en su lugar, utiliza la clave pública incluida con el mensaje.  
  
3.  El paso de procesamiento final de la canalización suele ser la resolución de entidades. Puede usar el Explorador de BizTalk o la consola de administración de BizTalk Server para crear entidades, asignarles un certificado de firma o crear alias de entidad. Todas las partes que defina en el Explorador de BizTalk tienen un identificador único de entidad (PID). BizTalk Server obtiene el PID y lo pone en el contexto del mensaje. BizTalk obtiene el PID mediante uno de estos métodos:  
  
    1.  Si el remitente firmó el mensaje, si el controlador de recepción pudo obtener un certificado de cliente o si se seleccionó la opción de resolver la entidad con el certificado, BizTalk utiliza la firma o el certificado de cliente correspondientes para buscar el PID. Debe configurar la entidad con el certificado como una propiedad antes de comenzar a recibir sus mensajes. Para obtener más información acerca de cómo configurar la entidad, consulte [con certificados para la resolución de entidades](../core/using-certificates-for-party-resolution.md).  
  
    2.  Si el remitente no utilizó un certificado de firma en el mensaje y se ha seleccionado la opción de resolver la entidad utilizando el Id. de seguridad del remitente (SSID), el componente de resolución de entidades utiliza el SSID para buscar el PID. Debe configurar la entidad para que use el SSID como alias antes de comenzar a recibir sus mensajes. Para obtener más información sobre el componente de resolución de entidades, vea [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).  
  
        > [!NOTE]
        >  BizTalk Server usa el nombre de cuenta en lugar del SID de Windows real cuando define alias para entidades.  
  
    3.  Si no se puede resolver la entidad, la canalización establece el PID en Invitado.  
  
4.  Si se marcó el puerto de recepción como de autenticación necesaria y BizTalk Server obtuvo un PID válido y lo resolvió como una entidad conocida, el mensaje se agrega a la cola de la base de datos de cuadro de mensajes. Si el SSID está en blanco o el PID es un Id. de invitado, BizTalk Server descarta el mensaje o lo envía a la cola de suspensión (según la configuración de la propiedad de autenticación necesaria). Puede utilizar la propiedad de autenticación necesaria para minimizar el efecto negativo de recibir una gran cantidad de mensajes de una entidad desconocida. Para obtener más información acerca de las opciones de autenticación para puertos de recepción, consulte [cómo configurar opciones de autenticación para un puerto de recepción](../core/how-to-configure-authentication-options-for-a-receive-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Autenticación de mensajes entre procesos](../core/authentication-of-messages-between-processes.md)   
 [Protección de mensajes salientes](../core/outbound-message-protection.md)   
 [Autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md)   
 [Autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md)   
 [Cómo configurar el servidor BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)