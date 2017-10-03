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
ms.openlocfilehash: 6c39e55ca233ef9875d3d56d25312ef879e3c539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
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
 [Mediante el inicio de sesión único](../core/using-single-sign-on3.md)