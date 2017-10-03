---
title: "Cómo limpiar el Equipo2 destino | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cleaning target computer
ms.assetid: 0d25930e-0bee-4658-80e7-4a1ab4a8131d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15614af9a42489693d535896245254208379d76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clean-the-target-computer"></a>Cómo limpiar el equipo de destino
Implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.  
  
### <a name="to-clean-the-target-computer"></a>Para limpiar el equipo de destino  
  
-   Quite los puertos de envío y las ubicaciones de recepción vinculadas a la orquestación.  
  
     Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:  
  
     \<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs  
  
     \<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs  
  
     Por ejemplo, en un símbolo del sistema, ejecute:  
  
     **cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**  
  
## <a name="see-also"></a>Vea también  
 [Implementación de puertos y ensamblados](../core/deploying-ports-and-assemblies2.md)