---
title: Cómo diagnosticar problemas con el adaptador HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110ae50f97d89b12b361a14caaac4f0df56989e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015725"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a><span data-ttu-id="27681-102">Cómo diagnosticar problemas con el adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="27681-102">How to Diagnose Problems with the HTTP Adapter</span></span>
<span data-ttu-id="27681-103">Esta sección contiene los pasos que se pueden seguir para diagnosticar problemas con el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="27681-103">This section contains steps that can be followed to help diagnose problems with the HTTP adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="27681-104">Comprobar si existen errores detallados en los archivos de registro de IIS y HTTPERR del servidor IIS</span><span class="sxs-lookup"><span data-stu-id="27681-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="27681-105">Los archivos de registro del servidor IIS de origen o de destino pueden contener información útil para la solución de problemas con el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="27681-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the HTTP adapter.</span></span> <span data-ttu-id="27681-106">De forma predeterminada, los archivos de registro de IIS de un servidor de Windows se ubican en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="27681-106">By default the IIS log files on a Windows Server are located in the following directory:</span></span>  
  
   <span data-ttu-id="27681-107"><em>% WinDir %\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="27681-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="27681-108">*% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="27681-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="27681-109">De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="27681-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="27681-110"><em>% WinDir %\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="27681-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="27681-111">El archivo de registro de HTTPERR está disponible solo en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27681-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a><span data-ttu-id="27681-112">Aislar problemas con el adaptador de envío HTTP al enviar a la URL de destino con un cliente que utiliza la clase System.Net.HttpWebRequest</span><span class="sxs-lookup"><span data-stu-id="27681-112">Isolate problems with the HTTP send adapter by posting to the destination URL with a client that uses the System.Net.HttpWebRequest class</span></span>  
  
1.  <span data-ttu-id="27681-113">Si el adaptador de envío HTTP genera errores al enviar a la URL de destino, cree un cliente que utilice las clases System.Net.HttpWebRequest y HttpWebResponse para enviar a la URL de destino.</span><span class="sxs-lookup"><span data-stu-id="27681-113">If the HTTP send adapter is generating errors when posting to the destination URL, create a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes to post to the destination URL.</span></span> <span data-ttu-id="27681-114">Este enfoque le ayudará a determinar si el problema es específico del adaptador de envío HTTP o si existe un problema de envío a la URL de destino en general.</span><span class="sxs-lookup"><span data-stu-id="27681-114">This approach will help determine if the problem is specific to the HTTP send adapter or if there is a problem posting to the destination URL in general.</span></span>  
  
2.  <span data-ttu-id="27681-115">Para obtener más información acerca de cómo crear un cliente que utiliza las clases System.Net.HttpWebRequest y HttpWebResponse vea [cómo usar las nuevas clases de System.Net para crear un cliente HTTP](http://go.microsoft.com/fwlink/?LinkId=66987).</span><span class="sxs-lookup"><span data-stu-id="27681-115">For more information about creating a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes see [How to use the new System.Net classes to create an HTTP client](http://go.microsoft.com/fwlink/?LinkId=66987).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27681-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="27681-116">See Also</span></span>  
 <span data-ttu-id="27681-117">[Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="27681-117">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="27681-118">Solucionar problemas del adaptador HTTP</span><span class="sxs-lookup"><span data-stu-id="27681-118">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)