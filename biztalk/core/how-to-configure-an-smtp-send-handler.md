---
title: "Cómo configurar un controlador de envío SMTP | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-10-22
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, SMTP adapters
- SMTP adapters, send handlers
- configuring [SMTP adapters], send handlers
ms.assetid: b68a36ce-f0a5-4302-a405-bb154c935f47
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99dc71cf04d8a80b3a88630908a814957c83b8cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-smtp-send-handler"></a>Cómo configurar un controlador de envío de SMTP
Puede configurar las propiedades del controlador de envío de SMTP en la consola de administración de BizTalk. Estas propiedades del controlador de envío se utilizan como valores de configuración del puerto de envío si las propiedades no se establecen en el puerto de envío de SMTP individual.  
  
### <a name="to-change-global-variables-for-an-smtp-send-handler"></a>Para cambiar las variables globales de un controlador de envío de SMTP  
  
1.  En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **SMTP**, en el panel derecho, haga el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host con la que asociará el controlador de envío y, a continuación, haga clic en **Propiedades**.  
  
4.  En el **propiedades de transporte SMTP** cuadro de diálogo, en la **propiedades** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre del servidor SMTP y el puerto TCP**|**[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> Requerido. Escriba el nombre del servidor SMTP y el número de puerto TCP (opcional) para usar al enviar mensajes. Por ejemplo, puede escribir:<br /><br /> -MiServidorSMTP<br />-mySMTPserver.internet.com:2525<br /><br /> **En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  (incluidos BizTalk Server 2013), escriba solo el nombre del servidor SMTP. Puerto TCP 25 está codificado de forma rígida.<br /><br /> Longitud máxima: 256|  
    |**De (dirección de correo electrónico)**|Requerido. Escriba la dirección de correo electrónico para colocar en el protocolo SMTP **de** encabezado.<br /><br /> Longitud máxima: 256|  
    |**Tipo de autenticación**|Escriba el tipo de autenticación que se utilizará con el servidor SMTP.<br /><br /> Opciones:<br /><br /> -   **Sin autenticación**<br />-   **Autenticación básica**<br />-   **Cuenta de proceso (NTLM)**<br /><br /> Valor predeterminado: (NTLM) de la cuenta de proceso|  
    |**Nombre de usuario.**|Escriba el nombre de usuario que se utilizará para la autenticación con el servidor SMTP.<br /><br /> Esta propiedad necesita un valor si **tipo de autenticación** es **la autenticación básica**.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
    |**Contraseña**|Escriba la contraseña que se utilizará para la autenticación con el servidor SMTP.<br /><br /> Esta propiedad necesita un valor si **tipo de autenticación** es **la autenticación básica**.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de SMTP](../core/configuring-the-smtp-adapter.md)