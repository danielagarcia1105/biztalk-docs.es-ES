---
title: Cómo configurar certificados con un adaptador de HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2f454f-22b5-4113-9a23-e00a816d5e48
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520204a6c0f411f8f622838b846a3af41b6c60a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007101"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a>Cómo configurar certificados con un adaptador de HTTP
El adaptador de envío HTTP puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente. Si se especifica un certificado de cliente, el adaptador de envío HTTP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente. Si no se especifica el certificado de cliente y el servidor de destino requiere certificados de cliente, el remitente no está autenticado y HTTP se produce un error de adaptador para enviar el mensaje de envío y sigue la lógica de reintentos estándar.  

 El adaptador de envío HTTP usará el certificado de cliente ubicado en el almacén personal de la cuenta bajo la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El certificado se especifica mediante la huella digital. Si, por cualquier motivo, el adaptador de envío HTTP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.  

 Cuando se usa un adaptador de HTTP para enviar un mensaje firmado o cifrado, configurar la huella digital del certificado SSL propiedades de transporte HTTP para el puerto de envío. En esta propiedad, especifique la huella digital del certificado que se usará para la autenticación de mensajes.  

## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a>Para configurar BizTalk Server para enviar mensajes a través de una conexión HTTP  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, crear un puerto de envío HTTP nuevo o abra las propiedades de puerto de envío HTTP existente.  

2. Haga clic en **configurar** en la sección de transporte de la **propiedades de puerto de envío** cuadro de diálogo.  

3. Haga clic en **autenticación** en el **propiedades de transporte HTTP** cuadro de diálogo.  

4. En **tipo de autenticación**, seleccione **Anonymous**, **básica**, **Digest**, o **Kerberos**.  

5. Si el tipo de autenticación es **básica** o **implícita**, seleccione **no use Single Sign-On** (en cuyo caso debe especificar el nombre de usuario y contraseña) o seleccione  **Usar inicio de sesión único** (en cuyo caso debe seleccionar la aplicación afiliada).  

6. En **huella digital de certificado de cliente SSL**, escriba la huella digital adecuada.  

7. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.
