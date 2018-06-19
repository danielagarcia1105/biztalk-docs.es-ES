---
title: Contexto de seguridad del adaptador de recepción de SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3db2b534-db9d-4075-aaad-0974b024dc71
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b381ba9b4e0e1d53eca8e6cdd01b9770eb82372f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223828"
---
# <a name="swift-receive-adapter-security-context"></a>Contexto de seguridad del adaptador de recepción de SWIFT
El adaptador de recepción, a diferencia del adaptador de envío, se inicia desde la línea de comandos de vínculo SWIFTNet (SNL/RA) (SWIFTNet inicio). El ejecutable del adaptador de recepción está configurado en el archivo de configuración de SNL/RA (paramconfig). El adaptador en el inicio inicializa la biblioteca SNL basándose en el parámetro de línea de comandos. Los valores de configuración se almacenan en caché para su uso posterior.  
  
 En la siguiente ilustración muestra la configuración del contexto de seguridad del adaptador de recepción.  
  
 ![Contexto de seguridad del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [URI del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [La inicialización del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [Modos sincrónico y diferido del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)   
 [Adaptador de almacenamiento y reenvío de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)