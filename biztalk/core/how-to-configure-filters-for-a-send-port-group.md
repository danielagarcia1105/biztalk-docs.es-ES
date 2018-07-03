---
title: Cómo configurar filtros para un grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send port groups
- send port groups, filters
- send port groups, configuring
- configuring, send port groups
- managing [send port groups], filters
- managing [send port groups], configuring
ms.assetid: 4c4bb408-5146-4740-a1d4-0ee72ec123fb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1960c8587f77be4f974095f5f663dba81bcb8f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970581"
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a>Cómo configurar filtros para un grupo de puertos de envío
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar uno o varios filtros para un grupo de puertos de envío. Los filtros pueden utilizarse para crear aplicaciones de enrutamiento por contenidos (CBR) o de mensajería simple. Un filtro establece condiciones para las propiedades o los campos de mensaje que determinan qué mensajes se enrutan al grupo de puertos de envío. Un filtro no filtra los mensajes que una orquestación enruta al grupo de puertos de envío.  
  
 Es posible crear una o varias expresiones de filtro formadas por una propiedad de mensaje, un operador y un valor validado con respecto a la propiedad mediante el operador.  
  
 Por ejemplo, podría crear una expresión similar a lo siguiente:  
  
 MSMQ.MsgID = 1  
  
 Con este filtro, el grupo de puertos de envío sólo se suscribirá a mensajes cuyo Id. de mensaje de MSMQ sea 1.  
  
 Puede crear expresiones adicionales y especificar la existencia de una relación con AND u OR entre estas expresiones y otras; por ejemplo:  
  
 MSMQ.MsgID = 1 OR  
  
 SMTP.From = MyServer  
  
 En este caso, el grupo de puertos de envío se suscribirá a todos los mensajes cuyo Id. de mensaje de MSMQ sea 1 o que se hayan enviado desde un servidor SMTP denominado MyServer.  
  
> [!NOTE]
>  Si crea un filtro para un grupo de puertos de envío en una aplicación que utilice un esquema de propiedades en otra aplicación y si, a continuación, importa la primera aplicación en un nuevo grupo de BizTalk, no recibirá ninguna advertencia de la falta del esquema, y el filtrado no se efectuará una vez instalada e iniciada la aplicación. Puede corregir el problema importando la aplicación que contiene el esquema antes de instalar la aplicación que no contiene el esquema.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede configurar filtros para un grupo de puertos de envío durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-filters-for-a-send-port-group"></a>Para configurar filtros para un grupo de puertos de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar un filtro de grupo de puertos de envío.  
  
3. Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío, haga clic en **propiedades**y, a continuación, haga clic en **filtros**.  
  
4. Configurar filtros como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Eliminar**|Eliminar la expresión de filtro seleccionada.|  
   |**Subir**|Subir la propiedad seleccionada en la secuencia de expresión de filtro.|  
   |**Bajar**|Bajar la propiedad seleccionada en la secuencia de expresión de filtro.|  
   |**Propiedad**|En la lista, hacer clic en una propiedad de mensaje para utilizarla en esta expresión de filtro.|  
   |**Operador**|Escribir o seleccionar el operador para la expresión.|  
   |**Value**|Escribir el valor que se validará con la propiedad. El tipo de valor aceptado varía en función del tipo de propiedad. Para ver qué tipo de valor se acepta para una propiedad, coloque el puntero del mouse sobre ésta. Los valores aceptables son como sigue: Int: (entero) debe ser un número entero. Cadena: Cadena de caracteres. fecha y hora: fecha y hora en. Formato compatible con NET. Para obtener más información sobre formatos de fecha y hora compatibles con .NET, vea "DateTimeFormatInfo Class" en la Ayuda de .NET Framework.|  
   |**Agrupar por**|Seleccione **y** o **o** para indicar la relación entre las expresiones de filtro.|  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)