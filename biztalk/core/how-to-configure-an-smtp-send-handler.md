---
title: Cómo configurar un controlador de envío SMTP | Microsoft Docs
ms.custom: ''
ms.date: 2015-10-22
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SMTP adapters
- SMTP adapters, send handlers
- configuring [SMTP adapters], send handlers
ms.assetid: b68a36ce-f0a5-4302-a405-bb154c935f47
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42e5dc69199ccdfef2e671b8901b90a958a5a77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004173"
---
# <a name="how-to-configure-an-smtp-send-handler"></a>Cómo configurar un controlador de envío de SMTP
Puede configurar las propiedades del controlador de envío de SMTP en la consola de administración de BizTalk. Estas propiedades del controlador de envío se utilizan como valores de configuración del puerto de envío si las propiedades no se establecen en el puerto de envío de SMTP individual.  

### <a name="to-change-global-variables-for-an-smtp-send-handler"></a>Para cambiar las variables globales de un controlador de envío de SMTP  

1. En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **SMTP**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con la que asociará el controlador de envío y, a continuación, haga clic en **Propiedades**.  

4. En el **propiedades de transporte SMTP** cuadro de diálogo el **propiedades** ficha, realice lo siguiente:  


   |             Use              |                                                                                                                                                                                                                                                             Para                                                                                                                                                                                                                                                             |
   |-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Nombre del servidor SMTP y el puerto TCP** | **[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> Requerido. Escriba el nombre del servidor SMTP y el número de puerto TCP (opcional) para usar al enviar mensajes. Por ejemplo, puede escribir:<br /><br /> -MiServidorSMTP<br />-mySMTPserver.internet.com:2525<br /><br /> **En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  (incluido BizTalk Server 2013), escriba solo el nombre del servidor SMTP. Puerto TCP 25 está codificado de forma rígida.<br /><br /> Longitud máxima: 256 |
   |     **(Dirección de correo electrónico)**     |                                                                                                                                                                                                               Requerido. Escriba la dirección de correo electrónico para colocar en el protocolo SMTP **desde** encabezado.<br /><br /> Longitud máxima: 256                                                                                                                                                                                                               |
   |      **Tipo de autenticación**      |                                                                                                                                          Escriba el tipo de autenticación que se utilizará con el servidor SMTP.<br /><br /> Opciones:<br /><br /> -   **Sin autenticación**<br />-   **Autenticación básica**<br />-   **Cuenta de proceso (NTLM)**<br /><br /> Valor predeterminado: (NTLM) de la cuenta de proceso                                                                                                                                          |
   |           **Nombre de usuario.**           |                                                                                                                                                Escriba el nombre de usuario que se usará para la autenticación con el servidor SMTP.<br /><br /> Esta propiedad requiere un valor si **tipo de autenticación** es **autenticación básica**.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256                                                                                                                                                |
   |           **Contraseña**            |                                                                                                                                                Escriba la contraseña que se utilizará para la autenticación con el servidor SMTP.<br /><br /> Esta propiedad requiere un valor si **tipo de autenticación** es **autenticación básica**.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256                                                                                                                                                 |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de SMTP](../core/configuring-the-smtp-adapter.md)