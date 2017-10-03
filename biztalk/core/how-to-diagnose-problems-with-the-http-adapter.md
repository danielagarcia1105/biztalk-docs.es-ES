---
title: "Cómo diagnosticar problemas con el adaptador de HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 545e095624c30b4611c74dcfbdead13d685164ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a>Cómo diagnosticar problemas con el adaptador de HTTP
Esta sección contiene los pasos que se pueden seguir para diagnosticar problemas con el adaptador de HTTP.  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>Comprobar si existen errores detallados en los archivos de registro de IIS y HTTPERR del servidor IIS  
  
-   Los archivos de registro del servidor IIS de origen o de destino pueden contener información útil para la solución de problemas con el adaptador de HTTP. De forma predeterminada, los archivos de registro de IIS de un servidor de Windows se ubican en el siguiente directorio:  
  
     *% WinDir %\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.  
  
     De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:  
  
     *% WinDir %\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  El archivo de registro de HTTPERR está disponible solo en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a>Aislar problemas con el adaptador de envío HTTP al enviar a la URL de destino con un cliente que utiliza la clase System.Net.HttpWebRequest  
  
1.  Si el adaptador de envío HTTP genera errores al enviar a la URL de destino, cree un cliente que utilice las clases System.Net.HttpWebRequest y HttpWebResponse para enviar a la URL de destino. Este enfoque le ayudará a determinar si el problema es específico del adaptador de envío HTTP o si existe un problema de envío a la URL de destino en general.  
  
2.  Para obtener más información acerca de cómo crear un cliente que utiliza las clases System.Net.HttpWebRequest y HttpWebResponse vea [cómo usar las nuevas clases de System.Net para crear un cliente HTTP](http://go.microsoft.com/fwlink/?LinkId=66987).  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solucionar problemas del adaptador HTTP](../core/troubleshooting-the-http-adapter.md)