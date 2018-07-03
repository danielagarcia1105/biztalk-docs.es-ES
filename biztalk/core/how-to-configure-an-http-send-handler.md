---
title: Cómo configurar un controlador de envío HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, HTTP adapters
- configuring [HTTP adapters], send handlers
- HTTP adapters, send handlers
ms.assetid: 821bf30c-b220-4ded-953d-7e745c0698b9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3db1c7dd108bbd2aa9eb35dc4e3c3d7edba2f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000405"
---
# <a name="how-to-configure-an-http-send-handler"></a>Cómo configurar un controlador de envío HTTP
Utilice el siguiente procedimiento para cambiar el host con el que está asociado el controlador de envío HTTP.  

> [!NOTE]
>  Cada host puede tener solo un controlador de envío asociado a él.  
> 
> [!CAUTION]
>  Al usar controladores de adaptador de HTTP o de SOAP, se recomienda instalar las instancias de host de estos controladores en equipos de Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].  

### <a name="to-change-global-variables-for-an-http-send-handler"></a>Para cambiar las variables globales para un controlador de envío HTTP  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **HTTP**, en el panel derecho el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de envío.  

4. En el **propiedades** ficha, realice lo siguiente.  


   |         Use          |                                                                                                                                                                                                 Para                                                                                                                                                                                                  |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Tiempo de espera de solicitud (seg.)** | Especificar el tiempo de espera de una respuesta del servidor en segundos.<br /><br /> Si se establece en cero (0), el adaptador de HTTP calcula el tiempo de espera en función del tamaño del mensaje de solicitud.<br /><br /> Si no proporciona ningún valor, se usa el valor del controlador.<br /><br /> **Valor predeterminado:** 0<br /><br /> **Tipo:** largo<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** MAX_LONG |
   |   **Número máximo de redirecciones**   |                                                                                                       Especificar el número máximo de redirecciones permitidas para el mensaje que se está enviando.<br /><br /> **Valor predeterminado:** 5<br /><br /> **Tipo:** Int<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** 10                                                                                                       |
   |     **Tipo de contenido**      |                                                                 Especificar el tipo de contenido de los mensajes de solicitud.<br /><br /> Si no proporciona ningún valor, se usa el valor del controlador.<br /><br /> **Valor predeterminado:** Text/XML<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256                                                                  |


5. En el **Proxy** ficha, realice lo siguiente.  


   |   Use    |                                                                                                                          Para                                                                                                                           |
   |---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Utilizar proxy** |                                                                Especificar si el controlador de envío HTTP utiliza el servidor proxy.<br /><br /> **Valor predeterminado:** False<br /><br /> **Tipo:** booleano                                                                |
   |  **Server**   |               Especificar la dirección del servidor proxy para este puerto de envío.<br /><br /> Esta propiedad requiere un valor si **utilizar proxy** es **True**.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256                |
   |   **Puerto**    | Especificar el puerto del servidor proxy para este puerto de envío.<br /><br /> Esta propiedad requiere un valor si **utilizar proxy** es **True**.<br /><br /> **Valor predeterminado:** 80<br /><br /> **Tipo:** largo<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** 65535 |
   | **Nombre de usuario.** |      Especificar el nombre de usuario que se utilizará para la autenticación en el servidor proxy.<br /><br /> Esta propiedad requiere un valor si **utilizar proxy** es **True**.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256       |
   | **Contraseña**  |        Especificar la contraseña de usuario para la autenticación con el servidor proxy.<br /><br /> Esta propiedad requiere un valor si **utilizar proxy** es **True**.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256        |


6. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de HTTP](../core/configuring-the-http-adapter.md)