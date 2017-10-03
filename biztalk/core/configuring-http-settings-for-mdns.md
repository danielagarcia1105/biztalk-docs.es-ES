---
title: "Configuración de HTTP para MDN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c877e85-7887-43a9-9fd4-0853b573213f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74ba2eaf11e8beed3e28d10beb9f95b2f0f6194
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-http-settings-for-mdns"></a>Configuración de valores HTTP para MDNs
Como parte de la configuración HTTP relacionada con MDN, puede especificar las propiedades que espera el servidor web que recibe los MDN.  
  
> [!IMPORTANT]
>  Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-mdn-related-http-settings"></a>Para configurar los valores de HTTP relacionados con MDN  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **configuración HTTP para MDN**.  
  
3.  Seleccione el **error de coincidencia de nombre del certificado SSL omitir** aceptarán casilla de verificación para asegurarse de que si el nombre del servidor no coincide con el nombre del servidor que se generó el certificado SSL, debe tener una conexión SSL.  
  
4.  Haga clic en **expect de HTTP 100 continue** para establecer el encabezado Expect de HTTP a 100-continue, que especifica que los datos enviados no se incluirán en la solicitud HTTP inicial, pero espera a que el servidor solicite el contenido.  
  
5.  Haga clic en **activa la conexión HTTP mantener** para solicitar que una conexión HTTP se mantenga activa una vez completado un ciclo de solicitud y respuesta.  
  
6.  Haga clic en **expandir encabezados HTTP** para desplegar el encabezado content-type HTTP en una sola línea.  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del Host Local (AS2)](../core/configuring-local-host-settings-as2.md)