---
title: Configurar puertos dinámicos en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: 4d6569f9-e513-47f3-b2c1-4c21bafb2bf2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea1a63bf66cd798656f1303513b5200a49243138
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216188"
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a>Configurar puertos dinámicos en el adaptador SAP
## <a name="use-message-context-properties"></a>Usar propiedades de contexto de mensaje
En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. Dado que [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante las propiedades de contexto de mensaje.  
  
 Para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el URI, acción y enlace podrían se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en la forma de expresión, tal como se muestra en el ejemplo siguiente:  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET";  
Request2(WCF.BindingType)="sapBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="sap://CLIENT=800;LANG=EN;@A/YourSAPHost/00";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  Si está usando un adaptador de WCF-SAP en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, donde **SAPAdapter** es el nombre con el que agregó el adaptador de WCF-SAP en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.  
  
 En el ejemplo anterior:  
  
-   Se está creando Solicitud2 mensaje del mensaje Solicitud1. Los mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
-   PuertoEnvío es el nombre del puerto de envío lógico en la orquestación de BizTalk.  
  
 La forma de expresión es parte de la orquestación de BizTalk. Al implementar la orquestación, también se crea el puerto de envío WCF-Custom.  
  
 Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configurar dinámica enviar puertos usando adaptadores de propiedades de contexto WCF](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)