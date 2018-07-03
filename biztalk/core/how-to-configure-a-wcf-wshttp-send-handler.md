---
title: Cómo configurar un controlador de envío WCF-WSHttp | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, global variables
- configuring [WCF-WSHttp adapters], send handlers
- configuring [WCF-WSHttp adapters], global variables
- send handlers, WCF-WSHttp adapters
ms.assetid: b2c30edb-8f7b-4d3c-812b-5b877c47fda1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe3ba5d5338403b5ebfa0796ca4a31963e251d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014757"
---
# <a name="how-to-configure-a-wcf-wshttp-send-handler"></a>Cómo configurar un controlador de envío WCF-WSHttp
Para configurar el controlador de envío WCF-WSHttp, siga este procedimiento:  

> [!CAUTION]
>  Al utilizar controladores de adaptador de WCF-WSHttp, se recomienda instalar las instancias de host de estos controladores en equipos [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].  

### <a name="to-change-global-variables-for-a-wcf-wshttp-send-handler"></a>Para cambiar las variables globales de un controlador de envío WCF-WSHttp  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **WCF-WSHttp**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de recepción.  

4. En el **General** ficha, haga clic en **propiedades**, en el **Proxy** ficha, realice lo siguiente.  


   |   Use    |                                                                                                                                                                                                                        Para                                                                                                                                                                                                                        |
   |---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Utilizar proxy** |                                                                                                                                                                              Indicar si el puerto de envío usa un servidor proxy.<br /><br /> Esta opción está desactivada de forma predeterminada.                                                                                                                                                                              |
   |  **Dirección**  |                      Especificar la dirección del servidor proxy. Use la **https** o **http** esquema según la configuración de seguridad. Esta dirección puede ir seguida de dos puntos y el número de puerto. Por ejemplo, http://127.0.0.1:8080.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.                      |
   | **Nombre de usuario.** | Especificar el nombre de usuario que se utilizará para la autenticación. Si se usa la autenticación integrada o básica, el nombre de usuario incluye el dominio, es decir, dominio\nombre de usuario. Si se usa la autenticación implícita, el nombre de usuario no tiene dominio\\.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía. |
   | **Contraseña**  |                                                                                             Especificar la contraseña que se utilizará para la autenticación.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.                                                                                             |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de WCF-WSHttp](../core/configuring-the-wcf-wshttp-adapter.md)