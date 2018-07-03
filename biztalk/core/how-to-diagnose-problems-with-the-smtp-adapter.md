---
title: Cómo diagnosticar problemas con el adaptador de SMTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5a1f88d6d096b697f8fceb3c81f8527fa5f7342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010317"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a>Cómo diagnosticar problemas con el adaptador de SMTP
Esta sección contiene los pasos que pueden seguirse para diagnosticar los problemas del adaptador de SMTP.  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a>Comprobar la existencia de errores en los archivos de registro de SMTP del servidor SMTP  
  
- El destino de los archivos de registro del servidor SMTP puede contener información útil para la solución de problemas del adaptador de SMTP. De forma predeterminada, en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de SMTP se encuentran en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\SMTPSVC1\  
  
  > [!NOTE]
  >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor SMTP.  
  > 
  > [!NOTE]
  >  El registro de SMTP está deshabilitado de forma predeterminada en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]. Para obtener información acerca de cómo habilitar el registro de SMTP, vea la documentación de Windows Server.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solucionar problemas del adaptador de SMTP](../core/troubleshooting-the-smtp-adapter.md)