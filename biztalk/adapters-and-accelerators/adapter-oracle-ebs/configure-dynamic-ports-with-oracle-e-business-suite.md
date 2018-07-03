---
title: Configurar puertos dinámicos con Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2f960560a631dd2eaf36f43522513242c240e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981917"
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a>Configurar puertos dinámicos con Oracle E-Business Suite
En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. Dado que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante las propiedades de contexto de mensaje.  
  
 Para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** dar forma, como se muestra en el ejemplo siguiente:  
  
```  
Request2=Request1;  
Request2(WCF.Action)="InterfaceTables/Insert/OFA/FA/FA_BOOKS";  
Request2(WCF.BindingType)="oracleEBSBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracleebs://ebs_instance";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
> [!NOTE]
>  Si está usando un adaptador de WCF-OracleEBS de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`, donde **OracleEBSAdapter** es el nombre con el que se ha agregado el adaptador de WCF-OracleEBS [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.  
  
 En el ejemplo anterior,  
  
- Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1. Ambos mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
- Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.  
  
  El **expresión** forma es parte de la orquestación de BizTalk. Implementación de la orquestación también crea un puerto de envío WCF-Custom.  
  
  Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)