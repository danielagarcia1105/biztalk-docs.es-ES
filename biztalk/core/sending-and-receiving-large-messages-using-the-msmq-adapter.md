---
title: Enviar y recibir mensajes de gran tamaño mediante el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, large messages
- configuring [MSMQ adapters], large messages
- MSMQ adapters, large messages
ms.assetid: 208efbed-7b58-4da5-ba27-65a315c2713b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a23265be84f2767849e4d61c2e9a95bfc9ed4ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269532"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a>Enviar y recibir mensajes de gran tamaño mediante el adaptador de MSMQ
El control de mensajes predeterminado del adaptador de MSMQ depende, en parte, del tamaño del mensaje en cuestión. Cuando un mensaje tiene un tamaño inferior a cuatro megabytes (4 MB), el adaptador de MSMQ utiliza la biblioteca de clases de .NET Framework. De lo contrario, utiliza extensiones de mensajes de gran tamaño de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Si la aplicación recibe o envía de forma sistemática mensajes de gran tamaño, puede que resulte necesario controlar la cantidad de memoria que utiliza el adaptador. Para obtener más información acerca del ahorro de memoria, vea [optimizar el rendimiento del adaptador de MSMQ](../core/optimizing-performance-of-the-msmq-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento del adaptador de MSMQ](../core/optimizing-performance-of-the-msmq-adapter.md)   
 [Configurar el adaptador MSMQ](../core/configuring-the-msmq-adapter.md)