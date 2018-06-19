---
title: Cómo configurar BizTalk Server para recibir mensajes SMIME o MIME cifrado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d72002c8-6bd8-458f-8149-1c0c4cbbb682
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd9778d6fb37058cfb70d476590b5d32fe8936e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008765"
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a>Cómo configurar BizTalk Server para recibir mensajes SMIME o MIME cifrado
Este tema describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usar certificados para recibir mensajes cifrados de MIME/SMIME. El procedimiento siguiente también se aplica a la configuración de la recepción de mensajes cifrados mediante transporte AS2.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe iniciar sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a>Para configurar BizTalk Server para recibir mensajes cifrados  
  
1.  Crear una canalización para recibir mensajes cifrados, como se indica a continuación:  
  
    > [!NOTE]
    >  Este paso no es necesario al configurar el transporte de AS2 para recibir mensajes cifrados, puesto que las canalizaciones AS2Receive y AS2EdiReceive que se incluyen en BizTalk Server sirven esta función.  
  
    > [!NOTE]
    >  El componente de canalización de descodificador de MIME/SMIME realiza tanto el descifrado como la validación de la firma digital (cuando se configura para que realice las dos funciones). Por tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes cifrados y firmados, puede usar la misma canalización de recepción. Es decir, no tiene que crear canalizaciones diferentes para el descifrado y para la validación de la firma digital.  
  
    1.  Crear una canalización de recepción y, a continuación, arrastre el componente de canalización de descodificador de MIME/SMIME en la fase de descodificación de la canalización.  
  
    2.  En el **propiedades** ventana, configurar las propiedades de componente de canalización de descodificador de MIME/SMIME.  
  
        > [!NOTE]
        >  Configurar las propiedades del componente de canalización de descodificador de MIME/SMIME incluye la configuración de la propiedad Comprobar lista de revocación en True si desea comprobar la lista de revocación de certificados para los certificados que utilizan los remitentes para firmar los mensajes que se envían a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si deshabilita esta opción aumenta el rendimiento del componente. La lista de revocación de certificados asociada con un certificado se descarga desde el sitio Web de servicios de certificado adecuada. Si el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se puede conectar al sitio Web remoto, se produce un error de mensaje en la canalización.  
  
        > [!NOTE]
        >  Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk.  
  
    3.  Genere e implemente la canalización de recepción.  
  
2.  Configurar la ubicación de recepción para recibir mensajes cifrados, como se indica a continuación:  
  
    1.  Agregue el ensamblado de BizTalk que ha creado que contiene la canalización de recepción a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes cifrados.  
  
        > [!NOTE]
        >  Este paso no es necesario al configurar el transporte de AS2 para recibir mensajes cifrados, puesto que las canalizaciones AS2Receive y AS2EdiReceive se incluyen en la aplicación EDI de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    2.  Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el paso anterior.  
  
3.  Configurar el host se usa como el controlador de recepción para la ubicación de recepción con el certificado de descifrado, como se indica a continuación:  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, contextual BizTalk host que es el controlador para recibir mensajes cifrados y, a continuación, haga clic en **propiedades**.  
  
        > [!NOTE]
        >  Este procedimiento no es aplicable para el transporte de AS2 disponible con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Se aplica para el descodificador de MIME de BizTalk, no el descodificador AS2. El descodificador AS2 determinará el certificado en función de la información del certificado en el mensaje.  
  
    2.  En el **propiedades de Host** cuadro de diálogo, haga clic en **certificado**y, a continuación, haga clic en **examinar**.  
  
        > [!NOTE]
        >  El procedimiento anterior le permite configurar su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno de forma que sólo algunos hosts pueden recibir y procesar mensajes concretos. Cuando se configura un host con la huella digital de un certificado que se usará para descodificar el mensaje y el descifrado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea una propiedad de la aplicación para ese host en la base de datos de cuadro de mensajes. Proteger los mensajes que se reciben y descifran con esta huella digital se enrutan únicamente a esta y a otros hosts que están configurados con esta huella digital.  
  
    3.  En el **Seleccionar certificado** cuadro de diálogo, seleccione el certificado de descifrado que instaló y, a continuación, cierre todos los cuadros de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar certificados para MIME o mensajes SMIME](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)