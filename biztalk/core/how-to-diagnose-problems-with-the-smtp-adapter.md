---
title: "Cómo diagnosticar problemas con el adaptador de SMTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a41a347534c07b522de5fc073933758870bf8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a><span data-ttu-id="2db58-102">Cómo diagnosticar problemas con el adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="2db58-102">How to Diagnose Problems with the SMTP Adapter</span></span>
<span data-ttu-id="2db58-103">Esta sección contiene los pasos que pueden seguirse para diagnosticar los problemas del adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="2db58-103">This section contains steps that can be followed to help diagnose problems with the SMTP adapter.</span></span>  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a><span data-ttu-id="2db58-104">Comprobar la existencia de errores en los archivos de registro de SMTP del servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="2db58-104">Check the SMTP log files of the SMTP Server for errors</span></span>  
  
-   <span data-ttu-id="2db58-105">El destino de los archivos de registro del servidor SMTP puede contener información útil para la solución de problemas del adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="2db58-105">The target SMTP server log files can contain information that is helpful for troubleshooting problems with the SMTP adapter.</span></span> <span data-ttu-id="2db58-106">De forma predeterminada, en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de SMTP se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="2db58-106">By default the SMTP log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
     <span data-ttu-id="2db58-107">*% WinDir %\\*system32\LogFiles\SMTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="2db58-107">*%WinDir%\\*system32\LogFiles\SMTPSVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2db58-108">*% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2db58-108">*%WinDir%* is a placeholder for the location of the Windows directory on the SMTP server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2db58-109">El registro de SMTP está deshabilitado de forma predeterminada en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2db58-109">SMTP logging is disabled by default on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="2db58-110">Para obtener información acerca de cómo habilitar el registro de SMTP, vea la documentación de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2db58-110">For information about enabling logging for SMTP, see the Windows Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db58-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2db58-111">See Also</span></span>  
 <span data-ttu-id="2db58-112">[Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="2db58-112">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="2db58-113">Solucionar problemas del adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="2db58-113">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)