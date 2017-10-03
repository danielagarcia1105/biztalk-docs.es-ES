---
title: Solucionar problemas de rendimiento con el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9e18a2f26af993da36a13d389f2aff2ad2f60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a>Solucionar problemas de rendimiento con el adaptador SAP
Esta sección describe el uso de técnicas de solución de problemas para resolver los problemas de rendimiento que pueden surgir al usar [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].  
  
##  <a name="BKMK_SAPSlowdown"></a>Degradación o pausa en el rendimiento al usar el adaptador con BizTalk Server  
 **Problema**  
  
 Cuando se usa el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el número de mensajes enviados o recibidos por el adaptador se ralentiza o se trata de una pausa.  
  
 **Causa**  
  
 El **EnableBizTalkCompatibilityMode** no está establecida la propiedad de enlace en WCF-Custom enviar o puerto de recepción en la consola de administración de BizTalk Server.  
  
 **Resolución**  
  
 Establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en True. Para obtener más información acerca de esta propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md). Para obtener instrucciones sobre cómo establecer una propiedad de enlace, consulte [configurar las propiedades de enlace para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).  
  
##  <a name="BKMK_SAPMemLeak"></a>Posible pérdida de memoria al usar valores NULL para los parámetros  
 **Problema**  
  
 Puede observar memoria perder en caso de no especificar valores para parámetros de entrada o una tabla al invocar artefactos en el sistema SAP.  
  
 **Resolución**  
  
 Asegúrese de que se especifican valores para todos los parámetros de entrada y la tabla al invocar un artefacto en el sistema SAP.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)