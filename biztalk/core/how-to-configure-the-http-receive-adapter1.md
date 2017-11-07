---
title: "Cómo configurar la recepción HTTP < adaptador 1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6356a130b412ea849c79213ab55b000ea827f3a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a>Para configurar adaptador de recepción de HTTP
Puede usar el adaptador de recepción HTTP para enviar mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de recepción HTTP es una extensión ISAPI de Internet Information Services (IIS) que se hospeda en el proceso IIS.  
  
### <a name="to-configure-the-http-receive-adapter"></a>Para configurar el adaptador de recepción HTTP  
  
1.  Copie el HTTP (BTSHTTPReceive.dll) de adaptador de recepción de  **\<BizTalk > \HttpReceive >** a la carpeta que contiene el proyecto de inicio de sesión único (SSO), por ejemplo:  
  
     **< Adapter_install > \biztalk\SSO\mySSODemo**  
  
    1.  Agregue una nueva extensión de servicio Web mySSODemo.  
  
    2.  Busque y copie **< BizTalk_install > \HttpReceive** a la carpeta que contiene el proyecto SSO, por ejemplo:  
  
         **\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll < Adapter_install >.**  
  
    3.  Establecer el estado de extensión de servicio Web mySSODemo a **permitido**.  
  
2.  Reinicie IIS para aplicar todos los cambios.  
  
## <a name="see-also"></a>Vea también  
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)