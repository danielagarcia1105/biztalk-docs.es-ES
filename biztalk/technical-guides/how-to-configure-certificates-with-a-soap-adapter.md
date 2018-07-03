---
title: Cómo configurar certificados con un adaptador de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0a709ab6b28796328677e7e8ae009e3273565a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012285"
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a>Cómo configurar certificados con un adaptador de SOAP
El adaptador de envío SOAP puede ayudar a proteger una conexión con servidores que admitan o requieran certificados de cliente. Si se especifica un certificado de cliente, el adaptador de envío SOAP utilizará el certificado para conectarse a los servidores que requieran o admitan certificados de cliente. Si no especifica un certificado de cliente y el servidor de destino requiere certificados de cliente, no se autentica el remitente y el envío de SOAP adaptador no puede enviar el mensaje y seguirá la lógica de reintentos estándar.  

 El adaptador de envío SOAP utilizará el certificado de cliente ubicado en el almacén personal de la cuenta en la que se esté ejecutando el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de SOAP especifica el certificado por su huella digital. Si, por cualquier motivo, el adaptador de envío SOAP no consigue cargar el certificado, el mensaje que se intentaba enviar quedará suspendido.  

 Cuando se usa un adaptador de SOAP para enviar un mensaje firmado o cifrado, configurar la propiedad de transporte de SOAP de huella digital del certificado de cliente para el puerto de envío.  

## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  

### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a>Para configurar BizTalk Server para enviar mensajes a través de una conexión de SOAP  

1. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, cree un nuevo puerto de envío SOAP o abra las propiedades de puerto de envío de un SOAP existente.  

2. Haga clic en **configurar** en el **transporte** sección de la **propiedades de puerto de envío** cuadro de diálogo.  

3. En el **General** ficha **tipo de autenticación**, seleccione **Anonymous**, **básica**, **Digest**, o **NTLM**.  

4. Si el tipo de autenticación es **básica** o **implícita**, seleccione **no use Single Sign-On** (en cuyo caso debe especificar el nombre de usuario y contraseña) o seleccione  **Usar inicio de sesión único** (en cuyo caso debe seleccionar la aplicación afiliada).  

5. En **huella digital de certificado de cliente SSL**, escriba la huella digital adecuada.  

6. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.
