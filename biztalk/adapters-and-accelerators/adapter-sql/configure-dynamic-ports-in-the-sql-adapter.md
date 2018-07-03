---
title: Configurar puertos dinámicos en el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98b66ed-0bf7-4b24-9d16-9792d033b818
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c23bce67dbc4eaca8441e6e7d07573724225cc45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976237"
---
# <a name="configure-dynamic-ports-in-the-sql-adapter"></a>Configurar puertos dinámicos en el adaptador de SQL
En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede configurar los puertos dinámicos para una [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]. Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un adaptador de WCF, puede configurar dinámicamente un puerto para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante las propiedades de contexto de mensaje.  

## <a name="use-an-expression-shape"></a>Usar una forma de expresión  
 Para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], el URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** dar forma, como se muestra en el ejemplo siguiente:  
  
```  
Request2=Request1;  
Request2(WCF.Action)="TableOp/Insert/dbo/CustomerTable";  
Request2(WCF.BindingType)="sqlBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="mssql://sql_server/my_instance/my_database";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  Si está usando un adaptador de WCF-SQL en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, también puede especificar el tipo de transporte como `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`, donde **SQLAdapter** es el nombre con el que se ha agregado el adaptador de WCF-SQL [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Consola de administración.  
  
 En el ejemplo anterior,  
  
- Se está creando la Solicitud2 mensaje del mensaje de la Solicitud1. Ambos mensajes se asignan a un esquema de operación, que se genera mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
- Puerto de envío es el nombre del puerto de envío lógico en la orquestación de BizTalk.  
  
  El **expresión** forma es parte de la orquestación de BizTalk. Implementación de la orquestación también crea un puerto de envío WCF-Custom.  
  
  Para obtener más información acerca de cómo configurar puertos dinámicos, consulte [configuración dinámica enviar puertos utilizando propiedades adaptadores de WCF contexto](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)