---
title: Solucionar problemas de rendimiento con el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6443dd8b96b19b3cf42f6444ba1ae6c16f2b4ee6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a>Solucionar problemas de rendimiento con el adaptador de Siebel
Esta sección describe el uso de técnicas de solución de problemas para resolver los problemas de rendimiento que pueden surgir al usar [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  
  
## <a name="known-issues"></a>Problemas conocidos  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a>Degradación o pausa en el rendimiento al usar el adaptador con BizTalk Server  
 **Problema**  
  
 Cuando se usa el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el número de mensajes enviados o recibidos por el adaptador se ralentiza o se trata de una pausa.  
  
 **Causa**  
  
 El **EnableBizTalkCompatibilityMode** no está establecida la propiedad de enlace en WCF-Custom enviar o puerto de recepción en la consola de administración de BizTalk Server.  
  
 **Resolución**  
  
 Establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en True. Para obtener más información acerca de esta propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md). Para obtener instrucciones sobre cómo establecer una propiedad de enlace, consulte [configurar las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)