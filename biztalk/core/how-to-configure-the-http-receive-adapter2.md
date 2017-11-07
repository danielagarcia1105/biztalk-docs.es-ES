---
title: "Cómo configurar la recepción HTTP < adaptador 2 | Documentos de Microsoft"
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
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6e40036308aa872a2d6ba23da8209ee9f80cfc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a>Para configurar adaptador de recepción de HTTP
El adaptador de recepción HTTP se puede usar para enviar mensajes a BizTalk Server. El adaptador de recepción HTTP es una extensión ISAPI de Internet Information Services (IIS) que se hospeda en el proceso IIS.  
  
### <a name="to-configure-the-http-receive-adapter"></a>Para configurar el adaptador de recepción HTTP  
  
1.  Copie el HTTP (BTSHTTPReceive.dll) de adaptador de recepción de  **\<BizTalk2010 > \HttpReceive >** a la carpeta que contiene el proyecto de inicio de sesión único (SSO) (por ejemplo, **< Adapter_install > \ biztalk2010\SSO\mySSODemo**).  
  
    1.  Agregue una nueva extensión de servicio Web mySSODemo.  
  
    2.  Busque y copie <BizTalk_install>\HttpReceive a la carpeta que contiene su proyecto SSO, por ejemplo,  
  
         <Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.  
  
    3.  Establecer el estado de extensión de servicio Web mySSODemo a **permitido**.  
  
2.  Reinicie IIS para asegurarse de que todos los cambios entran en vigor.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)