---
title: Configurar puertos dinámicos en el adaptador de SAP | Microsoft Docs
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
ms.openlocfilehash: de45553cfad2db19cfe16bbcd55420019b4971e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971509"
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a>Configurar puertos dinámicos en el adaptador de SAP
## <a name="use-message-context-properties"></a>Usar propiedades de contexto de mensaje
En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. Dado que [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante las propiedades de contexto de mensaje.  
  
 Para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en la forma de expresión, tal como se muestra en el ejemplo siguiente:  
  
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
>  Si está usando un adaptador de SAP de WCF en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, donde **SAPAdapter** es el nombre con el que se ha agregado el adaptador SAP de WCF en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.  
  
 En el ejemplo anterior:  
  
- Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1. Los mensajes que se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
- Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.  
  
  La forma de expresión es parte de la orquestación de BizTalk. Al implementar la orquestación, también se crea el puerto de envío WCF-Custom.  
  
  Para obtener más información sobre cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)