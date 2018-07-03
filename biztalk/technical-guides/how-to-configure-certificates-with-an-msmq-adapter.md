---
title: Cómo configurar certificados con un adaptador de MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 922a171d-705f-4465-acda-212aa3797c57
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c73c695423ac8b0e9a08ee375e1294f74f832a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972445"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a>Cómo configurar certificados con un adaptador de MSMQ
El adaptador de envío MSMQ puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente. Si se especifica un certificado de cliente, el adaptador de envío MSMQ utiliza el certificado al conectarse a los servidores que requieran o admitan certificados de cliente. Si no se especifica el certificado de cliente y el servidor de destino requiere certificados de cliente, no se autentica el remitente y de envío MSMQ adaptador no puede enviar el mensaje y seguirá la lógica de reintentos estándar.  

 MSMQ adaptador de envío utiliza el certificado de cliente desde el almacén personal de la cuenta bajo la que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso se está ejecutando. El certificado se especifica mediante la huella digital. Si se produce un error en el adaptador de envío MSMQ cargar el certificado por cualquier motivo, se suspende el mensaje que se intentaba enviar.  

 Cuando se usa un adaptador de MSMQ para enviar un mensaje firmado o cifrado, configurar la propiedad de transporte de MSMQ de huella digital de certificado para el puerto de envío. En esta propiedad, especifique la huella digital del certificado que se usará para la autenticación de mensajes. Utilizar esta propiedad en combinación con la propiedad Utilizar autenticación para comprobar el mensaje. Utilizar las propiedades Nombre de usuario y Contraseña para obtener acceso a las colas.  

## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a>Para configurar BizTalk Server para enviar mensajes a través de una conexión de MSMQ  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, cree un nuevo puerto de envío MSMQ o abra las propiedades de puerto de envío MSMQ existente.  

2. Haga clic en **configurar** en el **transporte** sección de la **propiedades de puerto de envío** cuadro de diálogo.  

3. En el **propiedades de transporte de MSMQ** cuadro de diálogo para **autenticación**, seleccione **True**.  

4. Para **huella digital del certificado**, escriba la huella digital adecuada.  

5. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.
