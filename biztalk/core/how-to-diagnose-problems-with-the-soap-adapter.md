---
title: Cómo diagnosticar problemas con el adaptador de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85c585c3fae6c6f49412f00e02276276e9c73b64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968317"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a><span data-ttu-id="6a182-102">Cómo diagnosticar problemas con el adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="6a182-102">How to Diagnose Problems with the SOAP Adapter</span></span>
<span data-ttu-id="6a182-103">Esta sección contiene los pasos que se pueden seguir para diagnosticar problemas con el adaptador de SOAP.</span><span class="sxs-lookup"><span data-stu-id="6a182-103">This section contains steps that can be followed to help diagnose problems with the SOAP adapter.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="6a182-104">Compruebe si existen errores detallados en el registro de IIS y HTTPERR del servidor IIS</span><span class="sxs-lookup"><span data-stu-id="6a182-104">Check the IIS log and HTTPERR log of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="6a182-105">El origen o el destino de los archivos de registro del servidor IIS pueden contener información útil para la solución de problemas con el adaptador de SOAP.</span><span class="sxs-lookup"><span data-stu-id="6a182-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the SOAP adapter.</span></span> <span data-ttu-id="6a182-106">De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="6a182-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="6a182-107"><em>% WinDir %\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="6a182-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6a182-108">*% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="6a182-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="6a182-109">De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="6a182-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="6a182-110"><em>% WinDir %\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="6a182-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6a182-111">El archivo de registro de HTTPERR está disponible solo en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a182-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a182-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a182-112">See Also</span></span>  
 <span data-ttu-id="6a182-113">[Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="6a182-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="6a182-114">Solucionar problemas del adaptador SOAP</span><span class="sxs-lookup"><span data-stu-id="6a182-114">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)