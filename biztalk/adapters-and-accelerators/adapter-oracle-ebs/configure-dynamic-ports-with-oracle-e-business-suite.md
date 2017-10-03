---
title: "Configurar puertos dinámicos con Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b02dc0cd4a4cf1d031acaf6d5a0e1c905ee225b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a>Configurar puertos dinámicos con Oracle E-Business Suite
En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. Dado que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante las propiedades de contexto de mensaje.  
  
 Para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], el URI, la acción y el enlace pueden se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** forma, tal y como se muestra en el ejemplo siguiente:  
  
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
>  Si está usando un adaptador de WCF-OracleEBS en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`, donde **OracleEBSAdapter** es el nombre con el que agregó el adaptador de WCF-OracleEBS [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.  
  
 En el ejemplo anterior,  
  
-   Se está creando Solicitud2 mensaje del mensaje Solicitud1. Los mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
-   PuertoEnvío es el nombre del puerto de envío lógico en la orquestación de BizTalk.  
  
 El **expresión** forma es parte de la orquestación de BizTalk. Implementación de la orquestación, también crea un puerto de envío WCF-Custom.  
  
 Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configurar dinámica enviar puertos usando adaptadores de propiedades de contexto WCF](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)