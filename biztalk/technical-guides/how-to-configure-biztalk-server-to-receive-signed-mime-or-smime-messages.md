---
title: "Cómo configurar BizTalk Server reciba firmado MIME o mensajes SMIME | Documentos de Microsoft"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88487fb96c89b8a611ab591223fa1820f70de1cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a>Cómo configurar BizTalk Server reciba firmado MIME o mensajes SMIME
Este tema describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usar certificados para recibir mensajes firmados de MIME/SMIME. El procedimiento siguiente también se aplica a la configuración de la recepción de mensajes firmados mediante transporte AS2.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe iniciar sesión como un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a>Para configurar BizTalk Server para recibir mensajes firmados  
  
1.  Crear una canalización para recibir mensajes firmados, como se indica a continuación:  
  
    > [!NOTE]
    >  Este paso no es necesario al configurar el transporte de AS2 para recibir mensajes firmados, porque los AS2Receive y AS2EdiReceive canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servir esta función.  
  
    1.  Crear una canalización de recepción y, a continuación, arrastre el componente de canalización de descodificador de MIME/SMIME a la fase de descodificación de la canalización de recepción.  
  
    2.  En el **propiedades** ventana, configurar las propiedades de componente de canalización de descodificador de MIME/SMIME.  
  
        > [!NOTE]
        >  Puede configurar propiedades de canalización para una ubicación de recepción después de que se haya implementado la canalización en un grupo de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede configurar diferentes propiedades de canalización para cada ubicación de recepción del grupo de BizTalk.  
  
    3.  Genere e implemente la canalización de recepción.  
  
2.  Configurar una ubicación de recepción para recibir mensajes firmados, como se indica a continuación:  
  
    1.  Agregue el ensamblado de BizTalk que ha creado que contiene la canalización de recepción a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes firmados.  
  
        > [!NOTE]
        >  Este paso no es necesario al configurar el transporte AS2 para recibir mensajes firmados, puesto que las canalizaciones AS2Receive y AS2EdiReceive se incluyen en la aplicación EDI de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    2.  Configure las ubicaciones de recepción en la aplicación de BizTalk con la canalización de recepción que creó en el procedimiento anterior.  
  
3.  Configurar la entidad con un certificado para recibir mensajes firmados, como se indica a continuación:  
  
    -   Abra la **propiedades de la entidad** cuadro de diálogo en la consola de administración de BizTalk Server, haga clic en el **certificado** , haga clic en **examinar**, seleccione el certificado adecuado, y, a continuación, haga clic en **Aceptar**.  
  
        > [!NOTE]
        >  El certificado usado para comprobar una firma para una entidad debe ser único entre los certificados usados para comprobar las firmas de las demás entidades.  
  
## <a name="see-also"></a>Vea también  
 [Configurar certificados para MIME o mensajes SMIME](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)