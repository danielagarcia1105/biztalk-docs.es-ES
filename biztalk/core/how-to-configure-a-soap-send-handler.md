---
title: Cómo configurar un controlador de envío SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SOAP adapters
- SOAP adapters, denial of service
- denital of service, HTTP adapters
- configuring [SOAP adapters], send handlers
- configuring [SOAP adapters], denial of service
- SOAP adapters, send handlers
- denial of service, SOAP adapters
ms.assetid: fd610a3f-ca10-42e0-b81e-219e07e33830
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4bcbe39861c37db348e1e37752fbad6d9616033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005485"
---
# <a name="how-to-configure-a-soap-send-handler"></a>Cómo configurar un controlador de envío SOAP
Para configurar el controlador de envío de SOAP, siga este procedimiento:  

> [!CAUTION]
>  Al usar controladores de adaptador HTTP o SOAP, se recomienda que instale las instancias de host de estos controladores en Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]equipos.  

### <a name="to-change-global-variables-for-a-soap-send-handler"></a>Para cambiar las variables globales de un controlador de envío de SOAP  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **SOAP**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de recepción.  

4. En el **Proxy** ficha, realice lo siguiente.  


   |   Use    |                                                                                                                  Para                                                                                                                   |
   |---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Utilizar proxy** |                                                                                          Indicar si el controlador de envío de SOAP utiliza un servidor proxy.                                                                                          |
   |  **Server**   |                  Especificar el nombre del servidor proxy.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256                   |
   |   **Puerto**    | Especificar el puerto que utiliza el controlador de envío de SOAP.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Valor predeterminado: 80<br /><br /> Tipo: long<br /><br /> Valor mínimo: 0<br /><br /> Valor máximo: 65535 |
   | **Nombre de usuario.** |             Especificar el nombre de usuario que se utilizará para la autenticación.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256             |
   | **Contraseña**  |             Especificar la contraseña que se utilizará para la autenticación.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256              |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de SOAP](../core/configuring-the-soap-adapter.md)   
 [Publicación de servicios web](../core/publishing-web-services.md)