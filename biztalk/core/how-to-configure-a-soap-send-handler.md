---
title: Cómo configurar un controlador de envío SOAP | Documentos de Microsoft
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
ms.openlocfilehash: 65ca116b47e36d754b27839a09225aeb313c9e0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248244"
---
# <a name="how-to-configure-a-soap-send-handler"></a>Cómo configurar un controlador de envío SOAP
Para configurar el controlador de envío de SOAP, siga este procedimiento:  
  
> [!CAUTION]
>  Al utilizar controladores de adaptador HTTP o SOAP, se recomienda instalar las instancias de host de estos controladores de Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]equipos.  
  
### <a name="to-change-global-variables-for-a-soap-send-handler"></a>Para cambiar las variables globales de un controlador de envío de SOAP  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **SOAP**, en el panel derecho, haga el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.  
  
4.  En el **Proxy** ficha, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Utilizar proxy**|Indicar si el controlador de envío de SOAP utiliza un servidor proxy.|  
    |**Server**|Especificar el nombre del servidor proxy.<br /><br /> Esta propiedad solo necesita un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
    |**Puerto**|Especificar el puerto que utiliza el controlador de envío de SOAP.<br /><br /> Esta propiedad solo necesita un valor si **utilizar proxy** está seleccionada.<br /><br /> Valor predeterminado: 80<br /><br /> Tipo: long<br /><br /> Valor mínimo: 0<br /><br /> Valor máximo: 65535|  
    |**Nombre de usuario.**|Especificar el nombre de usuario que se utilizará para la autenticación.<br /><br /> Esta propiedad solo necesita un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
    |**Contraseña**|Especificar la contraseña que se utilizará para la autenticación.<br /><br /> Esta propiedad solo necesita un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador SOAP](../core/configuring-the-soap-adapter.md)   
 [Publicar servicios Web](../core/publishing-web-services.md)